<script setup lang="ts">
import { ref } from "vue";

let showMenuBar = ref(true);
</script>

<template>
  <q-layout view="hHh LpR fFf">
    <!-- Fejléc -->
    <q-header v-model="showMenuBar" class="text-white" elevated style="background-color: #42a5f5">
      <q-toolbar>
        <q-tabs shrink>
          <q-route-tab label="Dolgozat Minta" to="/" />
          <q-route-tab label="Felhasználók" to="/creators" />
        </q-tabs>
      </q-toolbar>
    </q-header>
    <!-- A router ide (router-view) tölti be az oldalt -->
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<style lang="scss">
.active {
  background-color: #dddddd;
}

.toolbar-title-fontsize {
  font-size: 30px;
}
</style>
