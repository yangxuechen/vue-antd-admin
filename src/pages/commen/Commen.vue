<template>
  <div class="new-page" :style="`min-height: ${pageMinHeight}px`">
    <h1>常用组件</h1>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  name: "Commen",

  data() {
    return {};
  },
  computed: {
    ...mapState("setting", ["pageMinHeight"]),
    desc() {
      return this.$t("description");
    },
  },
};
</script>

<style lang="less" scoped>
@import "index";
</style>
