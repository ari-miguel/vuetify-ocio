<template>
  <v-app>

    <v-navigation-drawer v-model="drawer">


        <v-list nav class="pa-5">
          <v-list-item prepend-icon="mdi-email" title="Inbox" value="inbox" to="/"></v-list-item>
          <v-list-item prepend-icon="mdi-account-supervisor-circle" title="Supervisors" value="supervisors" to="/peliculas"></v-list-item>
          <v-list-item prepend-icon="mdi-clock-start" title="Clock-in" value="clockin"></v-list-item>
        </v-list>
      <!--  -->
    </v-navigation-drawer>

    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-app-bar-title>Ocio</v-app-bar-title>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>

    <AppFooter />
  </v-app>
</template>

<script setup>
import { ref } from 'vue';

const drawer = ref(false);
</script>
