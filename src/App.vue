<template>
  <div class="wrapper">
    <h1 class="title">Добавление товара</h1>
    <div class="sortButton">
      <Button title="По умолчанию" isGhost />
    </div>
    <div class="sidebar">
      <Sidebar />
    </div>
    <div class="topPageComponent">
      <TopPageComponent />
    </div>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar';
import TopPageComponent from './components/TopPageComponent';
import Button from './components/Button';

export default {
  name: 'App',
  components: {
    Sidebar,
    TopPageComponent,
    Button,
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  display: grid;
  grid-template-columns: auto 332px minmax(320px, 1044px) auto;
  grid-template-rows: 83px auto;
  min-height: 100vh;
  grid-template-areas: '. title sort .' '. sidebar topPageComponent .';
  padding: 0 15px 0 15px;
  margin-bottom: 16px;
  .sidebar {
    grid-area: sidebar;
    height: auto;
  }
  .topPageComponent {
    grid-area: topPageComponent;
  }
  .title {
    grid-area: title;
    justify-self: left;
    align-self: end;
    margin-bottom: 16px;
  }
  .sortButton {
    grid-area: sort;
    justify-self: right;
    align-self: end;
    margin-bottom: 16px;
  }
}
@media (max-width: 685px) {
  .wrapper {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(4 auto);
    grid-template-areas: 'title' 'sidebar' 'sort' 'topPageComponent';
  }
  .sortButton {
    margin-top: 16px;
  }
}
</style>
