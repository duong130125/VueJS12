<template>
  <div>
    <h2>Bài 10:</h2>
    <v-card>
      <v-card-title>Item</v-card-title>
      <v-data-table
        :headers.attr="headers"
        :items="items"
        class="elevation-1"
        :items-per-page="5"
        :footer-props="{
          'items-per-page-options': [5, 10, 15],
        }"
      >
        <!-- Slot để custom cột 'Status' -->
        <template v-slot:[`item.status`]="{ item }">
          <v-chip :color="getColor(item.status)" dark>
            {{ item.status }}
          </v-chip>
        </template>

        <!-- Slot để custom cột 'Budget' -->
        <template v-slot:[`item.budget`]="{ item }">
          <div>${{ item.budget }}</div>
        </template>
      </v-data-table>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Headers của bảng
      headers: [
        { text: "Name", value: "name", align: "start" },
        { text: "Project Name", value: "projectName" },
        { text: "Post", value: "post" },
        { text: "Status", value: "status" },
        { text: "Budget", value: "budget" },
      ],
      // Dữ liệu mẫu cho bảng
      items: [
        {
          name: "Sunil Joshi",
          projectName: "Elite Admin",
          post: "Web Designer",
          status: "Active",
          budget: 3.9,
        },
        {
          name: "Andrew McDownland",
          projectName: "Real Homes WP Theme",
          post: "Project Manager",
          status: "Pending",
          budget: 24.5,
        },
        {
          name: "Christopher Jamil",
          projectName: "MedicalPro WP Theme",
          post: "Project Manager",
          status: "Completed",
          budget: 12.8,
        },
        {
          name: "Nirav Joshi",
          projectName: "Hosting Press HTML",
          post: "Frontend Engineer",
          status: "Active",
          budget: 2.4,
        },
        {
          name: "Micheal Doe",
          projectName: "Helping Hands WP Theme",
          post: "Content Writer",
          status: "Cancel",
          budget: 9.3,
        },
      ],
    };
  },
  methods: {
    // Hàm để lấy màu sắc cho từng trạng thái
    getColor(status) {
      switch (status) {
        case "Active":
          return "green";
        case "Pending":
          return "orange";
        case "Completed":
          return "blue";
        case "Cancel":
          return "red";
        default:
          return "grey";
      }
    },
  },
};
</script>

<style scoped>
.v-data-table-header th {
  font-weight: bold;
  text-align: left;
}
.v-chip {
  font-weight: 500;
}
</style>
