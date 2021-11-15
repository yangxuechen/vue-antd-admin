<template>
  <div class="city-select-contariner">
    <a-select
      v-model:value="province"
      :options="provinceData"
       size="large"
      class="select-item"
      show-search
      placeholder="Select a province"
    >
    </a-select>
    <a-select
      v-model:value="secondCity"
      :options="computeCity"
       size="large"
      class="select-item"
      show-search
      placeholder="Select a city"
    >
    </a-select>
  </div>
</template>

<script>
import * as MyCityData from './CityData'
export default {
  name: 'CitySelect',
  data() {
    return {
      province: '',
      secondCity: '',
      provinceData: MyCityData.provinceData,
      cityData: []
    }
  },
  mounted() {},
  watch: {
    province: function(newVal, oldVal) {
      console.log(newVal)
      this.secondCity = ''
    },
    secondCity: function(newVal, oldVal) {
      console.log(newVal)
      this.$emit('change', this.province + '' + this.secondCity)
    }
  },
  computed: {
    computeCity() {
      return MyCityData.getCityData(this.province)
    }
  },
  methods: {}
}
</script>

<style lang="less" scoped>
.city-select-contariner {
  width: 100%;
  display: flex;
  justify-content: space-between;
  gap: 10px;
  .select-item {
    width: 50%;
  }
}
</style>
