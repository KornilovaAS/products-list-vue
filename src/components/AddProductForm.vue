<template>
  <form>
    <div :class="$style.fieldset">
      <Input
        placeholder="Введите наименование товара"
        id="productName"
        label="Наименование товара"
        isRequired
      />
      <Textarea
        placeholder="Введите описание товара"
        id="productDesciption"
        label="Описание товара"
      />
      <Input
        placeholder="Введите ссылку"
        id="productUrl"
        label="Ссылка на изображение товара"
        isRequired
      />
      <Input
        placeholder="Введите цену"
        id="productPrice"
        label="Цена товара"
        isRequired
      />
      <Button title="Добавить товар" :class="$style.button" />
    </div>
  </form>
</template>
<script>
import Input from './Input';
import Textarea from './Textarea';
import Button from './Button';

export default {
  name: 'AddProductForm',
  components: {
    Input,
    Textarea,
    Button,
  },
};
</script>
<style lang="scss" module type="text/scss">
@import '.././styles/typography';
.fieldset {
  position: sticky;
  top: 1em;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(5 auto);
  gap: 16px;
  .button {
    margin-top: 8px;
  }
}
</style>
