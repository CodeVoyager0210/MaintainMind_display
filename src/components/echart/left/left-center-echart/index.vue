<template>
  <div>
    <Chart :cdata="cdata" />
  </div>
</template>

<script>
import Chart from './chart.vue'
export default {
  components: {
    Chart,
  },
  data() {
    return {
      cdata: {
        months: ['1月', '2月', '3月', '4月', '5月', '6月'],
        engine1: [1200, 1150, 1100, 1050, 1000, 950],
        engine2: [1000, 980, 950, 920, 880, 850],
        engine3: [800, 820, 810, 790, 770, 750]
      },
    }
  },

  mounted() {},
  beforeDestroy() {},
  methods: {},
}
</script>

<style lang="scss" scoped></style>
