<template>
  <div :class="$style.wrapper">
    <input
      :class="$style.input"
      :placeholder="placeholderTitle"
      :type="type"
      :id="id"
    />
  </div>
</template>

<script>
export default {
  name: 'Input',
  props: {
    placeholderTitle: {
      type: String,
    },
    type: {
      type: String,
      default: 'text',
    },
    id: {
      type: String,
    },
  },
};
</script>

<style lang="scss" module>
@import '.././styles/typography';
.wrapper {
  position: relative;
  .input {
    padding: 10px 16px;
    width: 100%;
    color: $color-fontInput;
    border: none;
    border-radius: 4px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    font-family: $font-family;
    font-weight: 400;
    font-size: 12px;
    line-height: 15.08px;
  }
}
</style>
