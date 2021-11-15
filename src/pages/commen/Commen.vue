<template>
  <div class="new-page" :style="`min-height: ${pageMinHeight}px`">
    <h1>常用组件</h1>
    <div class="box">
      <CitySelect></CitySelect>
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";
import CitySelect from "../../components/city/CitySelect.vue";
export default {
  name: "Commen",
  components: { CitySelect },
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
