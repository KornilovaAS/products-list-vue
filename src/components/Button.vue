<template>
  <button
    :class="[
      $style.btn,
      $style.default,
      { [$style.succes]: isSucces },
      { [$style.ghost]: isGhost },
    ]"
  >
    {{ title }}
    <IconBase
      v-if="isGhost"
      width="8"
      height="6"
      icon-name="arrow"
      viewBox="0 0 8 6"
      iconColor="none"
      :class="$style.svgArrow"
    >
      <IconArrow />
    </IconBase>
  </button>
</template>

<script>
import IconArrow from './icons/IconArrow';
import IconBase from './IconBase';
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
    isGhost: {
      type: Boolean,
      default: false,
    },
  },
  data: () => ({}),
  components: {
    IconArrow,
    IconBase,
  },
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
  transition: 0.3s;
  .svgArrow {
    margin-bottom: 0.5px;
  }
  &:hover {
    transform: scale(0.97);
  }
}
.default {
  color: $color-fontInput;
  background: $color-buttonDefault;
  letter-spacing: -0.02em;
  &:hover {
    background: $color-fontInput;
    color: $color-white;
  }
}
.succes {
  color: $color-white;
  background: $color-buttonSucces;
  letter-spacing: 0;
}
.ghost {
  color: $color-fontInput;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  padding: 10px 16px 10px 16px;
  &:hover {
    transform: scale(0.95);
    transition: 1s;
  }
}
</style>
