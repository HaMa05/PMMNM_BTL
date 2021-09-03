<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  props: ['revenueOfWeek'],
  mounted() {
    this.renderChart(
      {
        labels: [
          "Thứ 2",
          "Thứ 3",
          "Thứ 4",
          "Thứ 5",
          "Thứ 6",
          "Thứ 7",
          "Chủ nhật"
        ],
        datasets: [
          {
            label: "Doanh thu",
            data: this.revenueOfWeek,
            backgroundColor: "transparent",
            borderColor: "rgba(1, 116, 188, 0.50)",
            pointBackgroundColor: "rgba(171, 71, 188, 1)"
          }
        ]
      },
      {
        responsive: true,
        maintainAspectRatio: false,
        title: {
          display: true,
          text: "Doanh thu tuần này"
        }
      }
    );
  }
}
</script>
