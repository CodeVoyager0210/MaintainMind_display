<template>
  <div>
    <Echart
      :options="options"
      id="LeftBottomEchart"
      height="255px"
      width="100%"
    ></Echart>
  </div>
</template>

<script>
export default {
  props: {
    cdata: {
      type: Object,
      default: () => ({}),
    },
  },
  data() {
    return {
      options: {},
    }
  },
  watch: {
    cdata: {
      handler(newData) {
        this.options = {
          backgroundColor: 'transparent',
          radar: {
            indicator: [
              { name: '温度', max: 100 },
              { name: '压力', max: 100 },
              { name: '振动', max: 100 },
              { name: '转速', max: 100 },
              { name: '燃油效率', max: 100 },
              { name: '推力', max: 100 }
            ],
            center: ['50%', '50%'],
            radius: '80%',
            shape: 'polygon',
            splitNumber: 5,
            name: {
              textStyle: {
                color: '#fff',
                fontSize: 14
              }
            },
            splitLine: {
              lineStyle: {
                color: 'rgba(255, 255, 255, 0.2)'
              }
            },
            splitArea: {
              show: true,
              areaStyle: {
                color: ['rgba(255, 255, 255, 0.05)', 'rgba(255, 255, 255, 0.02)']
              }
            },
            axisLine: {
              lineStyle: {
                color: 'rgba(255, 255, 255, 0.3)'
              }
            }
          },
          series: [
            {
              name: '发动机状态',
              type: 'radar',
              data: [
                {
                  value: newData.engine1,
                  name: '发动机 #001',
                  lineStyle: {
                    color: '#5470c6',
                    width: 2
                  },
                  areaStyle: {
                    color: 'rgba(84, 112, 198, 0.3)'
                  },
                  symbol: 'circle',
                  symbolSize: 6
                },
                {
                  value: newData.engine2,
                  name: '发动机 #002',
                  lineStyle: {
                    color: '#91cc75',
                    width: 2
                  },
                  areaStyle: {
                    color: 'rgba(145, 204, 117, 0.3)'
                  },
                  symbol: 'circle',
                  symbolSize: 6
                }
              ]
            }
          ],
          color: ['#5470c6', '#91cc75'],
          legend: {
            data: ['发动机 #001', '发动机 #002'],
            bottom: 10,
            textStyle: {
              color: '#fff'
            }
          }
        }
      },
      immediate: true,
      deep: true,
    },
  },
  created() {},
  mounted() {},
  methods: {},
}
</script>
<style scoped lang="scss"></style>
