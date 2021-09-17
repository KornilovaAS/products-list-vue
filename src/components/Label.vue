<template>
  <div :class="$style.wrapper">
    <label :for="id" :class="$style.label">
      {{ description }}
      <span v-if="isRequired" :class="$style.requiredBlock"></span>
    </label>
  </div>
</template>

<script>
export default {
  name: 'Label',
  props: {
    id: {
      type: String,
    },
    description: {
      type: String,
    },
    isRequired: {
      type: Boolean,
      default: false,
    },
  },
  data: () => ({}),
};
</script>

<style lang="scss" module>
@import '.././styles/typography';
.wrapper {
  position: relative;
  .label {
    font-family: $font-family;
    font-size: 10px;
    line-height: 13px;
    letter-spacing: -0.02em;
    color: $color-fontLabel;
    &::after {
      content: '';
      position: absolute;
      top: 7px;
      display: inline-block;
      width: 4px;
      height: 4px;
      border-radius: 100%;
      background-color: $color-buttonDanger;
    }
  }
}
</style>
