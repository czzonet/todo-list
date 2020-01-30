<template>
  <div>{{a.msg}}</div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "BarDashboard",
  data() {
    return {
      a: {
        msg: "hello"
      }
    };
  }
});
</script>
