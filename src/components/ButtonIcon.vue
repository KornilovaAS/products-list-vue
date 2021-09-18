<template>
  <button :class="$style.btnIcon">
    <img :src="images" />
  </button>
</template>

<script>
import image from '../assets/card-foto.png';
export default {
  data: () => ({
    image,
  }),
};
</script>

<style lang="scss" module>
@import '.././styles/typography';
.btnIcon {
  width: 32px;
  height: 32px;
  background: $color-buttonDanger;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
}
</style>
