<template>
  <div class="cardContainer">
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
  </div>
</template>

<script>
import Card from './Card';
export default {
  name: 'TopPageComponent',
  components: {
    Card,
  },
};
</script>

<style lang="scss" scoped>
.cardContainer {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-left: 16px;
}
</style>
