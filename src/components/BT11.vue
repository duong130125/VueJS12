<template>
  <div>
    <h2>Bài 11:</h2>
    <v-container fluid class="pa-4">
      <v-row>
        <!-- Sidebar -->
        <v-col cols="12" md="3" lg="2">
          <v-select
            label="Gender"
            :items="['All']"
            variant="outlined"
            density="compact"
            class="mb-4"
            hide-details
          ></v-select>

          <v-card flat>
            <v-card-text class="pa-2">
              <h3 class="text-subtitle-1 font-weight-medium mb-2">
                Categories
              </h3>
              <v-checkbox
                v-for="category in categories"
                :key="category"
                v-model="selectedCategories"
                :label="category"
                :value="category"
                density="compact"
                hide-details
                class="mt-0 mb-1"
              ></v-checkbox>

              <h3 class="text-subtitle-1 font-weight-medium mt-4 mb-2">
                Colors
              </h3>
              <v-select
                label="Select colors"
                :items="[]"
                variant="outlined"
                density="compact"
                hide-details
              ></v-select>

              <h3 class="text-subtitle-1 font-weight-medium mt-4 mb-2">
                Price
              </h3>
              <v-checkbox
                v-for="range in priceRanges"
                :key="range"
                :label="range"
                :value="range"
                density="compact"
                hide-details
                class="mt-0 mb-1"
              ></v-checkbox>

              <h3 class="text-subtitle-1 font-weight-medium mt-4 mb-2">
                Rating
              </h3>
              <v-rating
                v-model="minRating"
                color="amber"
                half-increments
                size="small"
              ></v-rating>

              <v-btn color="primary" block class="mt-6">Reset Filters</v-btn>
            </v-card-text>
          </v-card>
        </v-col>

        <!-- Main content -->
        <v-col cols="12" md="9" lg="10">
          <v-row no-gutters align="center" class="mb-4">
            <v-col cols="auto">
              <h2 class="text-h5 font-weight-medium">Products</h2>
            </v-col>
            <v-col class="ml-auto" cols="12" sm="6" md="4">
              <v-text-field
                prepend-inner-icon="mdi-magnify"
                label="Search Products"
                single-line
                hide-details
                variant="outlined"
                density="compact"
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row>
            <v-col
              v-for="product in products"
              :key="product.id"
              cols="12"
              sm="6"
              md="4"
            >
              <v-card class="mx-auto" max-width="400">
                <v-img
                  :src="product.image"
                  height="250"
                  cover
                  class="align-end"
                >
                  <v-btn
                    icon="mdi-cart-plus"
                    variant="text"
                    color="white"
                    class="ma-2"
                  ></v-btn>
                </v-img>
                <v-card-title class="text-subtitle-1 font-weight-medium">{{
                  product.name
                }}</v-card-title>
                <v-card-text>
                  <div class="d-flex justify-space-between align-center">
                    <div>
                      <span class="text-primary font-weight-bold"
                        >${{ product.price }}</span
                      >
                      <span
                        class="text-caption text-decoration-line-through ml-2"
                        >${{ product.originalPrice }}</span
                      >
                    </div>
                    <v-rating
                      :model-value="product.rating"
                      color="amber"
                      density="compact"
                      half-increments
                      readonly
                      size="x-small"
                    ></v-rating>
                  </div>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script setup>
import { ref } from "vue";

const categories = ["All", "Kitchen", "Electronics"];
const selectedCategories = ref(["All"]);
const minRating = ref(3);
const priceRanges = [
  "$10 - $50",
  "$50 - $100",
  "$100 - $150",
  "$150 - $200",
  "Over $200",
];

const products = ref([
  {
    id: 1,
    name: "MacBook Air Pro",
    price: 15,
    originalPrice: 72,
    rating: 5,
    image: "https://picsum.photos/id/0/400/300",
  },
  {
    id: 2,
    name: "Red Velvet Dress",
    price: 16,
    originalPrice: 54,
    rating: 4.5,
    image: "https://picsum.photos/id/21/400/300",
  },
  {
    id: 3,
    name: "Boat Headphone",
    price: 36,
    originalPrice: 59,
    rating: 3.5,
    image: "https://picsum.photos/id/3/400/300",
  },
  {
    id: 4,
    name: "The Psychology of Money",
    price: 85,
    originalPrice: 649,
    rating: 5,
    image: "https://picsum.photos/id/24/400/300",
  },
  {
    id: 5,
    name: "Psalms Book for Growth",
    price: 89,
    originalPrice: 531,
    rating: 3.5,
    image: "https://picsum.photos/id/24/400/300",
  },
  {
    id: 6,
    name: "Gaming Console",
    price: 99,
    originalPrice: 399,
    rating: 2.5,
    image: "https://picsum.photos/id/96/400/300",
  },
]);
</script>
