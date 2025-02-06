<template>
    <v-navigation-drawer permanent>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">应用名称</v-list-item-title>
          <v-list-item-subtitle>侧边栏菜单</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
  
      <v-divider></v-divider>
  
      <v-list density="compact" nav>
        <v-list-item prepend-icon="mdi-home" title="首页" value="home"></v-list-item>
        <v-list-item prepend-icon="mdi-account" title="个人中心" value="profile"></v-list-item>
        <v-list-item prepend-icon="mdi-settings" title="设置" value="settings"></v-list-item>
      </v-list>
    </v-navigation-drawer>
  </template>
  
  <script>
  export default {
    name: 'Sidebar',
  };
  </script>