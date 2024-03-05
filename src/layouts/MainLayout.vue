<script setup lang="ts"></script>

<template>
  <q-layout view="hHh LpR fFf">
    <!-- Fejléc -->
    <q-header class="bg-blue-5 elevated text-white">
      <q-toolbar>
        <q-tabs inline-label>
          <q-route-tab label="Dolgozat minta" no-caps to="/advertisements" />
          <q-route-tab label="Készítők" no-caps to="/creators" />
        </q-tabs>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<style lang="scss">
.active {
  background-color: #dddddd;
}
</style>
