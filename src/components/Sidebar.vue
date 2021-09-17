<template>
  <div :class="$style.formWrapper">
    <h1>Sidebar</h1>
    <Button title="Добавить товар" isSucces />
    <Label id="productName" description="Наименование товара" isRequired />
    <Input placeholderTitle="Введите наименование товара" id="productName" />
  </div>
</template>

<script>
import Button from './Button';
import Input from './Input';
import Label from './Label';
export default {
  name: 'Sidebar',
  components: {
    Button,
    Input,
    Label,
  },
};
</script>

<style lang="scss" module>
@import '.././styles/typography';
.formWrapper {
  max-height: 440px;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  padding: 24px;
  background-color: $color-backgroundSecondary;
}
</style>
