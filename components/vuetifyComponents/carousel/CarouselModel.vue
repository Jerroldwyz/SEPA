<script setup lang="ts">
import { ref } from 'vue'

const colors = ref(['primary', 'secondary', 'yellow darken-2', 'red', 'orange'])

const model = ref(0)
</script>

<template>
  <!-- ----------------------------------------------------------------------------- -->
  <!-- Model -->
  <!-- ----------------------------------------------------------------------------- -->
  <div class="d-flex justify-space-around align-center py-4">
    <v-btn
      variant="text"
      icon="mdi-minus"
      @click="model = Math.max(model - 1, 0)"
    ></v-btn>
    {{ model }}
    <v-btn
      variant="text"
      icon="mdi-plus"
      @click="model = Math.min(model + 1, 4)"
    ></v-btn>
  </div>
  <v-carousel v-model="model">
    <v-carousel-item v-for="(color, i) in colors" :key="color" :value="i">
      <v-sheet :color="color" height="100%" tile>
        <div class="d-flex fill-height justify-center align-center">
          <div class="text-h2">Slide {{ i + 1 }}</div>
        </div>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>
