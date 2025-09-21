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
        time: ['00:00', '04:00', '08:00', '12:00', '16:00', '20:00', '24:00'],
        temperature: [720, 735, 750, 780, 810, 790, 760],
        pressure: [2200, 2250, 2300, 2350, 2400, 2380, 2320],
        vibration: [3.2, 3.5, 3.8, 4.2, 4.5, 4.1, 3.6]
      },
    }
  },
}
</script>
