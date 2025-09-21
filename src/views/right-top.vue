<template>
  <div id="RightTop">
    <dv-border-box-13>
      <HeaderTitle title="健康状态评估" />
      <div class="increase">
        <div class="rising">
          <dv-decoration-9 style="width: 100%; height: 100px; color: #5470c6"
            >850</dv-decoration-9
          >

          <p class="sizeone">剩余寿命(小时)</p>
        </div>
        <div class="rising">
          <dv-decoration-9 style="width: 100%; height: 100px; color: #91cc75"
            >5%</dv-decoration-9
          >
          <p class="sizetwo">故障概率</p>
        </div>
        <div class="rising">
          <dv-decoration-9 style="width: 100%; height: 100px; color: #ee6666"
            >92%</dv-decoration-9
          >
          <p class="sizeThree">整体健康度</p>
        </div>
      </div>
    </dv-border-box-13>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  created() {},
  mounted() {},
  methods: {},
}
</script>
<style scoped lang="scss">
#RightTop {
  height: 310px;
  width: 100%;
}
.increase {
  height: 250px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
.rising {
  width: 20%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}
</style>
