<template>
  <div>
    <dv-scroll-board
      style="width: 100%; height: 230px; padding: 0 20px"
      :config="config"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      config: {
        header: ['发动机编号', '运行周期', '压气机出口温度', '剩余寿命', '异常标签'],
        data: [
          ['ENG-001', '1250', '685°C', '850h', '温度异常'],
          ['ENG-002', '980', '712°C', '920h', '正常'],
          ['ENG-003', '1560', '698°C', '780h', '振动异常'],
          ['ENG-004', '2100', '725°C', '650h', '正常'],
          ['ENG-005', '875', '708°C', '1050h', '压力异常'],
          ['ENG-006', '1320', '692°C', '880h', '正常'],
          ['ENG-007', '1680', '718°C', '720h', '燃油效率低'],
          ['ENG-008', '760', '695°C', '1100h', '正常'],
          ['ENG-009', '1420', '708°C', '820h', '润滑异常'],
          ['ENG-010', '1950', '715°C', '690h', '正常'],
          ['ENG-011', '1120', '688°C', '950h', '启动失败'],
          ['ENG-012', '2280', '722°C', '580h', '正常'],
          ['ENG-013', '890', '705°C', '1020h', '传感器故障'],
          ['ENG-014', '1750', '712°C', '750h', '正常'],
          ['ENG-015', '1380', '698°C', '860h', '噪音异常'],
          ['ENG-016', '2050', '728°C', '620h', '正常'],
          ['ENG-017', '920', '692°C', '980h', '冷却异常'],
          ['ENG-018', '1580', '708°C', '800h', '正常'],
          ['ENG-019', '1180', '715°C', '910h', '推力不足'],
          ['ENG-020', '1820', '705°C', '710h', '正常']
        ],
        rowNum: 5,
        headerBGC: 'rgba(41, 105, 177,0.3)',
        oddRowBGC: 'transparent',
        evenRowBGC: 'transparent',
        hoverPause: false,
        columnWidth: [120, 100, 140, 100, 120],
        align: ['center', 'center', 'center', 'center', 'center'],
      },
    }
  },
  created() {},
  mounted() {},
  methods: {},
}
</script>
<style scoped lang="scss"></style>
