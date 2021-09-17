<template>
  <button :class="[$style.btn, $style.default, { [$style.succes]: isSucces }]">
    {{ title }}
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    title: {
      type: String,
      default: 'Добавить товар',
    },
    isSucces: {
      type: Boolean,
      default: false,
    },
  },
  data: () => ({}),
};
</script>

<style lang="scss" module>
@import '.././styles/typography';
.btn {
  display: inline-block;
  box-sizing: border-box;
  border-radius: 10px;
  text-align: center;
  border: none;
  font-family: $font-familyBtn;
  font-size: 12px;
  font-weight: 600;
  line-height: 15px;
  text-align: center;
  width: 100%;
  padding: 10px;
  cursor: pointer;
}
.default {
  color: $color-fontInput;
  background: $color-buttonDefault;
  letter-spacing: -0.02em;
}
.succes {
  color: $color-white;
  background: $color-buttonSucces;
  letter-spacing: 0;
}
</style>
