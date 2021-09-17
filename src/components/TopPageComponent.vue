<template>
  <div :class="$style.wrapper">
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

<style lang="scss" module>
.wrapper {
  display: flex;
  flex-wrap: wrap;
  gap: 16px 16px;
  margin-left: 16px;
}
</style>
