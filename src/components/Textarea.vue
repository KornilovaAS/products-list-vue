<template>
  <div class="wrapper">
    <label v-if="label" for="id" class="label">{{ label }}</label>
    <textarea
      class="textarea"
      :placeholder="placeholder"
      :id="id"
      :tabindex="1"
    />
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

<style lang="scss" scoped>
@import '.././styles/typography';
@import '.././styles/mixins';

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
    @include box-shadow(0px 2px 5px rgba(0, 0, 0, 0.1));
    font-family: $font-family;
    font-size: 12px;
    line-height: 15px;
    margin-top: 4px;
    height: 108px;
    resize: none;
    &::placeholder {
      color: rgba(180, 180, 180, 1);
    }
    &:focus {
      border: 1px solid $color-fontInput;
      outline: none;
    }
  }
}
</style>
