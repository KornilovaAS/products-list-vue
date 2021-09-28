<template>
  <div class="formWrapper">
    <AddProductForm />
  </div>
</template>

<script>
import AddProductForm from './AddProductForm';
export default {
  name: 'Sidebar',
  components: {
    AddProductForm,
  },
};
</script>

<style lang="scss" scoped>
@import '.././styles/typography';
@import '.././styles/mixins';

.formWrapper {
  position: sticky;
  top: 24px;
  width: 100%;
  max-width: inherit;
  padding: 24px;
  @include box-shadow(
    0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02)
  );
  border-radius: 4px;
  background-color: $color-backgroundSecondary;
}
</style>
