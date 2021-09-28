<template>
  <button
    :class="[
      $style.btn,
      $style.default,
      { [$style.succes]: isSucces },
      { [$style.ghost]: isGhost },
    ]"
    :tabindex="1"
  >
    {{ title }}
    <IconArrow v-if="isGhost" />
  </button>
</template>

<script>
import IconArrow from './icons/IconArrow';

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
  },
};
</script>

<style lang="scss" module type="text/scss">
@import '.././styles/typography';
@import '.././styles/mixins';
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

  &:hover {
    transform: scale(0.97);
  }
}
.default {
  color: rgba(180, 180, 180, 1);
  background: $color-buttonDefault;
  letter-spacing: -0.02em;
  &:hover {
    background-color: rgba(180, 180, 180, 1);
    color: $color-white;
  }
}
.succes {
  color: $color-white;
  background: $color-buttonSucces;
  letter-spacing: 0;
}
.ghost {
  font-family: $font-family;
  color: rgba(180, 180, 180, 1);
  border-radius: 4px;
  background: #fffefb;
  @include box-shadow(0px 2px 5px rgba(0, 0, 0, 0.1));
  padding: 10px 16px 10px 16px;
  &:hover {
    background: white;
    color: rgba(180, 180, 180, 1);
  }
}
</style>
