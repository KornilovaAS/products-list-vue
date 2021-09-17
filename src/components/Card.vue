<template>
  <div :class="$style.card">
    <img :src="image" :class="$style.imgCard" />
    <h2 :class="$style.title">Наименование товара</h2>
    <p :class="$style.descriptions">
      Довольно-таки интересное описание товара в несколько строк. Довольно-таки
      интересное описание товара в несколько строк
    </p>
    <span :class="$style.price">{{ priceRu }}</span>
    <ButtonIcon :class="$style.btnDelete" />
  </div>
</template>

<script>
import image from '../assets/card-foto.png';
import ButtonIcon from './ButtonIcon';
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
    ButtonIcon,
  },
};
</script>

<style lang="scss" module>
@import '.././styles/typography';
.card {
  position: relative;
  width: 332px;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(4 auto);
  grid-template-areas: 'img' 'title' 'descriptions' 'price';
  gap: 16px;
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
  .btnDelete {
    position: absolute;
  }
}
</style>
