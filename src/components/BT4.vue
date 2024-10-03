<template>
  <div class="text-center">
    <h2>Bài 4:</h2>
    <v-menu>
      <template v-slot:activator="{ props: menu }">
        <v-tooltip location="top">
          <template v-slot:activator="{ props: tooltip }">
            <v-btn color="primary" v-bind="mergeProps(menu, tooltip)">
              Quản trị viên
            </v-btn>
          </template>
          <span>I'm A Tooltip</span>
        </v-tooltip>
      </template>
      <v-list>
        <v-list-item v-for="(item, index) in items" :key="index">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>
<script>
import { mergeProps } from "vue";

export default {
  data: () => ({
    items: [
      { title: "Thông tin cá nhân" },
      { title: "Đổi mật khẩu" },
      { title: "Đăng xuất" },
    ],
  }),
  methods: {
    mergeProps,
  },
};
</script>
