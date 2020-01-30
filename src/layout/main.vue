<template>
  <div class="main-layout">
    <div class="header">
      <bar-header></bar-header>
    </div>
    <div class="body">
      <div class="side">
        <bar-side></bar-side>
      </div>
      <div class="content">
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>

<script>
/** component */
import BarHeader from "../menu/header/index";
import BarSide from "../menu/side/index";

export default {
  name: "MainLayout",
  components: { BarHeader, BarSide }
};
</script>

<style lang="scss" scoped>
.main-layout {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: stretch;

  height: 100%;

  .header {
    // flex-basis: 100px;
    flex: 0;
  }

  .body {
    flex: 1;
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: stretch;

    height: 100%;

    .side {
      flex-basis: 200px;
    }

    .content {
      flex: 1;
    }
  }
}
</style>