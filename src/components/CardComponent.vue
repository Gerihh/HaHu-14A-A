<template>
  <div class="q-pa-md row items-start q-gutter-md q-ma-lg">
    <q-card class="q-ma-lg">
      <q-card-section style="background-color: rgb(200, 190, 156)">
        <div>{{ id }}</div>
      </q-card-section>
      <q-card-section style="background-color: rgb(255, 228, 196)">
        <div></div>
      </q-card-section>
      <q-card-section style="background-color: rgb(200, 190, 156)">
        <div></div>
      </q-card-section>
      <q-card-section style="background-color: rgb(255, 228, 196)">
        <img src="asd" />
      </q-card-section>
      <q-card-section style="background-color: rgb(200, 190, 156)">
        <div class="text-h6"></div>
      </q-card-section>
      <q-card-section style="background-color: rgb(255, 228, 196); height: 50px">
        <q-btn class="bg-green-3 absolute-center">Hirdetés szerkesztése</q-btn>
      </q-card-section>
    </q-card>
  </div>
</template>

<script setup lang="ts">
import axios from "axios";
import { ref, onMounted } from "vue";

const id = ref();

onMounted(async () => {
  try {
    const response = await axios.get("http://localhost:3000/advertisements");
    id.value = response.data.id;
  } catch (error) {
    console.error("Error fetching advertisements:", error);
  }
});
</script>
