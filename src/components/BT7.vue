<template>
  <div class="text-center">
    <h2>Bài 7:</h2>
    <v-pagination v-model="page" :length="4" rounded="circle"></v-pagination>

    <v-pagination v-model="page" :length="4" rounded="0"></v-pagination>
  </div>
</template>
<script>
export default {
  data() {
    return {
      page: 1,
    };
  },
};
</script>
