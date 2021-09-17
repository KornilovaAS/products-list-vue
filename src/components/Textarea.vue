<template>
  <div :class="$style.wrapper">
    <label v-if="label" for="id" :class="$style.label">{{ label }}</label>
    <textarea :class="$style.textarea" :placeholder="placeholder" :id="id" />
  </div>
</template>

<script>
export default {
  name: 'Textarea',
  props: {
    placeholder: {
      type: String,
    },
    id: {
      type: String,
    },
    label: {
      type: String,
    },
  },
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
  }
  .textarea {
    width: 100%;
    padding: 10px 16px;
    color: $color-fontInput;
    border: none;
    border-radius: 4px;
    background: -internal-light-dark(rgb(255, 255, 255), rgb(59, 59, 59));
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    font-family: $font-family;
    font-size: 12px;
    line-height: 15px;
    margin-top: 4px;
    height: 108px;
    resize: none;
  }
}
</style>
