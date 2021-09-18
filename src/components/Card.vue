<template>
  <div :class="$style.wrapper">
    <div :class="$style.card">
      <img :src="image" :class="$style.imgCard" />
      <h2 :class="$style.title">Наименование товара</h2>
      <p :class="$style.descriptions">
        Довольно-таки интересное описание товара в несколько строк.
        Довольно-таки интересное описание товара в несколько строк
      </p>
      <span :class="$style.price">{{ priceRu }}</span>
    </div>
    <button :class="$style.btnDelete">
      <IconDelete />
    </button>
  </div>
</template>

<script>
import image from '../assets/card-foto.png';
import IconDelete from './icons/IconDelete';
export default {
  data: () => ({
    image,
    price: 10000,
  }),
  computed: {
    priceRu: function() {
      return this.price
        .toString()
        .replace(/\B(?=(\d{3})+(?!\d))/g, ' ')
        .concat(' руб.');
    },
  },
  components: {
    IconDelete,
  },
};
</script>

<style lang="scss" module>
@import '.././styles/typography';
@import '.././styles/mixins';
.wrapper {
  position: relative;
}
.card {
  position: relative;
  width: 332px;
  @include box-shadow(
    0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02)
  );
  border-radius: 4px;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(4 auto);
  grid-template-areas: 'img' 'title' 'descriptions' 'price';
  gap: 16px;
  cursor: pointer;
  .imgCard {
    grid-area: img;
  }
  .title {
    grid-area: title;
    font-family: $font-family;
    font-weight: 600;
    font-size: 20px;
    line-height: 25px;
    margin-left: 16px;
  }
  .descriptions {
    grid-area: descriptions;
    font-size: 16px;
    line-height: 20px;
    margin-top: 0;
    margin-bottom: 16px;
    margin-left: 16px;
    margin-right: 16px;
  }
  .price {
    grid-area: price;
    font-weight: 600;
    font-size: 24px;
    line-height: 30px;
    margin-left: 16px;
    margin-bottom: 24px;
  }
}
.btnDelete {
  position: absolute;
  width: 32px;
  height: 32px;
  background: $color-buttonDanger;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  top: -8px;
  right: -8px;
  border: none;
  cursor: pointer;
  transition: 0.2s;
  .svgDelete {
    text-align: center;
  }
  &:hover {
    transform: scale(0.97);
  }
}
</style>
