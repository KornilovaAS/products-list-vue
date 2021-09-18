<template>
  <div :class="$style.wrapper">
    <h1 :class="$style.title">Добавление товара</h1>
    <div :class="$style.sortButton">
      <Button title="По умолчанию" isGhost />
    </div>
    <Sidebar :class="$style.sidebar" />
    <TopPageComponent :class="$style.topPageComponent" />
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

<style lang="scss" module>
@import 'styles/typography.scss';
@import 'styles/global';
.wrapper {
  display: grid;
  grid-template-columns: auto 332px minmax(320px, 1044px) auto;
  grid-template-rows: 83px auto;
  min-height: 100vh;
  grid-template-areas: '. title sort .' '. sidebar topPageComponent .';
  .sidebar {
    grid-area: sidebar;
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
    padding-right: 16px;
  }
  .title {
    padding-left: 16px;
  }
}
</style>
