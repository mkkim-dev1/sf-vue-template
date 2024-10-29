<template>
  <v-app>
    <!-- 네비게이션 드로어 -->
    <v-navigation-drawer app v-model="drawer" color="grey lighten-4">
      <v-list>
        <v-list-item-group>
          <v-list-item v-for="(item, index) in menuItems" :key="index" link :to="item.route">
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <!-- 상단 바 -->
    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>My Vuetify Project</v-toolbar-title>
    </v-app-bar>

    <!-- 라우터 뷰 -->
    <v-main>
      <v-container>
        <router-view />
      </v-container>
    </v-main>

    <!-- 하단 바 -->
    <v-footer app>
      <v-col class="text-center">&copy; 2024 My Project</v-col>
    </v-footer>
  </v-app>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const drawer = ref(false);

const menuItems = [
  { title: "Home", icon: "mdi-home", route: "/" },
  { title: "About", icon: "mdi-information", route: "/about" },
  { title: "Contact", icon: "mdi-contact-mail", route: "/contact" },
  { title: "Book", icon: "mdi-book", route: "/book" },
];
</script>