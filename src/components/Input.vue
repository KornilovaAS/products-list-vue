<template>
  <div :class="$style.wrapper">
    <input
      :class="$style.input"
      :placeholder="placeholder"
      :type="type"
      :id="id"
      :required="isRequired"
      :tabindex="1"
    />
    <label v-if="label" :for="id" :class="$style.label">
      {{ label }}
    </label>
  </div>
</template>

<script>
export default {
  name: 'Input',
  props: {
    placeholder: {
      type: String,
    },
    type: {
      type: String,
      default: 'text',
    },
    id: {
      type: String,
    },
    isRequired: {
      type: Boolean,
      default: false,
    },
    label: {
      type: String,
    },
  },
};
</script>

<style lang="scss" module type="text/scss">
@import '.././styles/typography';
@import '.././styles/mixins';
input:required + label::after {
  content: '';
  position: absolute;
  display: inline-block;
  width: 4px;
  height: 4px;
  border-radius: 100%;
  background-color: $color-buttonDanger;
}
.wrapper {
  display: flex;
  flex-direction: column;
  position: relative;
  .input {
    padding: 10px 16px;
    width: 100%;
    color: $color-fontInput;
    border: none;
    border-radius: 4px;
    @include box-shadow(0px 2px 5px rgba(0, 0, 0, 0.1));
    font-family: $font-family;
    font-weight: 400;
    font-size: 12px;
    line-height: 15.08px;
    order: 2;
    margin-top: 4px;
    &::placeholder {
      color: rgba(180, 180, 180, 1);
    }
    &:focus {
      border: 1px solid $color-fontInput;
      outline: none;
    }
  }
  .label {
    font-family: $font-family;
    font-size: 10px;
    line-height: 13px;
    letter-spacing: -0.02em;
    color: $color-fontLabel;
    order: 1;
  }
}
</style>
