<template>
  <div class="d-flex justify-content-center" style="margin-top: 20px">
    <button class="btn btn-primary mx-2" @click="updateChart7">4D</button>
    <button class="btn btn-primary mx-2" @click="updateChart30">10D</button>
    <button class="btn btn-primary mx-2" @click="updateChart90">15D</button>
  </div>
  <div class="d-flex justify-content-center" style="margin-top: 20px">
    <apexchart
      ref="radar"
      width="550"
      type="line"
      :options="chartOptions"
      :series="series"
    ></apexchart>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      chartOptions: {
        chart: {
          id: "vuechart-example",
          toolbar: {
            show: true,
            tools: {
              download: true,
              selection: false,
              zoom: false,
              zoomin: false,
              zoomout: false,
              pan: false,
              reset: false | '<img src="/static/icons/reset.png" width="20">',
            },
          },
        },
        title: {
          text: "Binance smart chain price movement",
          align: "left",
        },
        xaxis: {
          type: "datetime",
          categories: ["16 Nov", "17 Nov", "18 Nov", "19 Nov"],
        },
      },
      series: [
        {
          name: "Binance smart chain",
          data: [1.5, 0.5, 1, 2],
        },
      ],
      yaxis: {
        title: {
          text: "Price, $",
        },
      },
    };
  },
  methods: {
    updateChart7() {
      const newData = [1.5, 0.5, 1, 2];
      this.$refs.radar.updateOptions({
        xaxis: {
          categories: ["16 Nov", "17 Nov", "18 Nov", "19 Nov"],
        },
      });
      this.series = [
        {
          data: newData,
        },
      ];
    },
    updateChart30() {
      const newData = [1.4, 1.2, 1, 0.8, 0.9, 1, 1.5, 0.5, 1, 2];
      this.$refs.radar.updateOptions({
        xaxis: {
          categories: [
            "09 Nov",
            "10 Nov",
            "11 Nov",
            "12 Nov",
            "13 Nov",
            "14 Nov",
            "15 Nov",
            "16 Nov",
            "17 Nov",
            "18 Nov",
            "19 Nov",
          ],
        },
      });
      this.series = [
        {
          data: newData,
        },
      ];
    },
    updateChart90() {
      const newData = [
        1, 2, 1.4, 1.3, 1.5, 1.4, 1.2, 1, 0.8, 0.9, 1, 1.5, 0.5, 1, 2,
      ];
      this.$refs.radar.updateOptions({
        xaxis: {
          categories: [
            "04 Nov",
            "05 Nov",
            "06 Nov",
            "07 Nov",
            "08 Nov",
            "09 Nov",
            "10 Nov",
            "11 Nov",
            "12 Nov",
            "13 Nov",
            "14 Nov",
            "15 Nov",
            "16 Nov",
            "17 Nov",
            "18 Nov",
            "19 Nov",
          ],
        },
      });
      this.series = [
        {
          data: newData,
        },
      ];
    },
  },
};
</script>
