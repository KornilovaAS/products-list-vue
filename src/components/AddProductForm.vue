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
        placeholder="Введите наименование товара"
        id="productPrice"
        label="Введите цену"
        isRequired
      />
      <Button title="Добавить товар" />
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
<style lang="scss" module>
@import '.././styles/typography';
.fieldset {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(5 auto);
  gap: 16px;
}
</style>
