<script setup lang="ts">
import { ref } from 'vue'

const panel = ref([0, 1])
const readonly = ref(false)
</script>

<template>
  <!-- ----------------------------------------------------------------------------- -->
  <!-- Readonly -->
  <!-- ----------------------------------------------------------------------------- -->
  <div class="d-flex">
    <v-checkbox v-model="readonly" label="Readonly"></v-checkbox>
  </div>

  <v-expansion-panels v-model="panel" :readonly="readonly" multiple>
    <v-expansion-panel>
      <v-expansion-panel-title>Panel 1</v-expansion-panel-title>
      <v-expansion-panel-text> Some content </v-expansion-panel-text>
    </v-expansion-panel>

    <v-expansion-panel>
      <v-expansion-panel-title>Panel 2</v-expansion-panel-title>
      <v-expansion-panel-text> Some content </v-expansion-panel-text>
    </v-expansion-panel>

    <v-expansion-panel>
      <v-expansion-panel-title>Panel 3</v-expansion-panel-title>
      <v-expansion-panel-text> Some content </v-expansion-panel-text>
    </v-expansion-panel>
  </v-expansion-panels>
</template>
