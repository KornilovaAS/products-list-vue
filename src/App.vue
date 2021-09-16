<template>
  <div :class="$style.wrapper">
    <Sidebar :class="$style.sidebar" />
    <TopPageComponent :class="$style.topPageComponent" />
  </div>
</template>

<script>
import Sidebar from './components/Sidebar';
import TopPageComponent from './components/TopPageComponent';

export default {
  name: 'App',
  components: {
    Sidebar,
    TopPageComponent,
  },
};
</script>

<style lang="scss" module>
@import 'styles/typography.scss';
@import 'styles/global';
.wrapper {
  padding-top: 30px;
  display: grid;
  grid-template-columns: auto 332px minmax(320px, 1440px) auto;
  grid-template-rows: auto;

  min-height: 100vh;
  grid-template-areas: '. sidebar topPageComponent .';
  .sidebar {
    grid-area: sidebar;
  }
  .topPageComponent {
    grid-area: topPageComponent;
  }
}
</style>
