<template>
  <div>
    <v-container>
      <v-card class="pa-6">
        <v-card-title>
          <h2 class="text-h5 font-weight-bold">Product List</h2>
        </v-card-title>

        <v-row class="mb-4 align-center">
          <v-col cols="12" sm="6">
            <v-text-field
              v-model="search"
              label="Search"
              append-inner-icon="mdi-magnify"
              single-line
              hide-details
              density="compact"
              class="search-input"
            ></v-text-field>
          </v-col>
          <v-spacer></v-spacer>
          <v-col cols="auto">
            <v-btn color="primary" class="add-item-btn">Add New Item</v-btn>
          </v-col>
        </v-row>

        <v-data-table
          :headers.attr="headers"
          :items="items"
          :search="search"
          class="elevation-1"
          :items-per-page="5"
          :footer-props="{
            'items-per-page-options': [5],
            'items-per-page-text': 'Items per page:',
            'show-current-page': true,
            'show-first-last-page': true,
          }"
        >
          <template #item.product_image="{ item }">
            <v-avatar size="40">
              <v-img :src="item.product_image" :alt="item.product"></v-img>
            </v-avatar>
          </template>

          <template #item.status="{ item }">
            <v-chip
              :color="item.status === 'Instock' ? 'green' : 'red'"
              size="small"
              class="text-capitalize status-chip"
            >
              {{ item.status }}
            </v-chip>
          </template>

          <template #item.actions="{ item }">
            <v-icon size="small" class="edit-icon me-2" @click="editItem(item)">
              mdi-pencil
            </v-icon>
            <v-icon size="small" class="delete-icon" @click="deleteItem(item)">
              mdi-delete
            </v-icon>
          </template>
        </v-data-table>
      </v-card>
    </v-container>
  </div>
</template>

<script setup>
import { ref } from "vue";

const search = ref("");

const headers = [
  {
    text: "Product Image",
    value: "product_image",
    align: "start",
    width: "120px",
  },
  { text: "Product", value: "product", align: "start", width: "200px" },
  { text: "Date", value: "date", width: "150px" },
  { text: "Status", value: "status", width: "120px" },
  { text: "Price", value: "price", width: "100px" },
  { text: "Actions", value: "actions", sortable: false, width: "100px" },
];

const items = ref([
  {
    product_image: "https://via.placeholder.com/40",
    product: "Curology Face wash",
    category: "Beauty",
    date: "Thu, Jan 12 2023",
    status: "Instock",
    price: "$275",
    selected: false,
  },
  {
    product_image: "https://via.placeholder.com/40",
    product: "Body Lotion",
    category: "Beauty",
    date: "Thu, Jan 20 2023",
    status: "Out of Stock",
    price: "$89",
    selected: false,
  },
  {
    product_image: "https://via.placeholder.com/40",
    product: "Smart Watch",
    category: "Electronics",
    date: "Fri, Feb 15 2024",
    status: "Instock",
    price: "$125",
    selected: false,
  },
  {
    product_image: "https://via.placeholder.com/40",
    product: "Camera",
    category: "Electronics",
    date: "Fri, March 30 2024",
    status: "Instock",
    price: "$200",
    selected: false,
  },
  {
    product_image: "https://via.placeholder.com/40",
    product: "Games",
    category: "Electronics",
    date: "Sat, March 30 2024",
    status: "Out of Stock",
    price: "$100",
    selected: false,
  },
]);

const editItem = (item) => {
  console.log("Edit item", item);
};

const deleteItem = (item) => {
  console.log("Delete item", item);
};
</script>

<style scoped>
.v-card {
  border-radius: 8px;
}

.v-card-title {
  font-size: 20px;
  font-weight: bold;
}

.search-input {
  max-width: 300px;
}

.add-item-btn {
  font-weight: bold;
  text-transform: none;
}

.v-data-table {
  background-color: white;
  border-radius: 10px;
}

.status-chip {
  font-weight: bold;
}

.edit-icon {
  color: #1976d2;
}

.delete-icon {
  color: #e53935;
}
</style>
