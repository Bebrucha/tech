<template>
  <div class="d-flex justify-content-center" style="margin-top: 20px">
    <button class="btn btn-primary mx-2" @click="updateChart7">10D</button>
    <button class="btn btn-primary mx-2" @click="updateChart30">20D</button>
    <button class="btn btn-primary mx-2" @click="updateChart90">30D</button>
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
          text: "Polygon price movement",
          align: "left",
        },
        xaxis: {
          type: "datetime",
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
      },
      series: [
        {
          name: "Polygon",
          data: [0.9, 1.2, 1.4, 1, 0.8, 0.5, 0.2, 0.4, 0.6, 0.8, 1],
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
      const newData = [0.9, 1.2, 1.4, 1, 0.8, 0.5, 0.2, 0.4, 0.6, 0.8, 1];
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
    updateChart30() {
      const newData = [
        1.2, 0.9, 1.4, 1.2, 1.1, 1.3, 1.1, 1, 1, 0.6, 0.7, 0.6, 0.4, 0.4, 0.5,
        1, 0.5, 0.2, 0.4, 0.6,
      ];
      this.$refs.radar.updateOptions({
        xaxis: {
          categories: [
            "31 Oct",
            "01 Nov",
            "02 Nov",
            "03 Nov",
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
    updateChart90() {
      const newData = [
        0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.3, 0.4, 0.3, 0.7, 1, 1.5, 1.5, 1.6, 1.4,
        1.2, 1, 0.6, 0.7, 0.6, 0.4, 0.4, 0.5, 1, 0.5, 0.2, 0.4, 0.6,
      ];
      this.$refs.radar.updateOptions({
        xaxis: {
          categories: [
            "21 Oct",
            "22 Oct",
            "23 Oct",
            "24 Oct",
            "25 Oct",
            "26 Oct",
            "27 Oct",
            "28 Oct",
            "29 Oct",
            "30 Oct",
            "31 Oct",
            "01 Nov",
            "02 Nov",
            "03 Nov",
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
