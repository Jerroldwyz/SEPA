<script setup lang="ts"></script>

<template>
  <!-- ----------------------------------------------------------------------------- -->
  <!-- Slide y -->
  <!-- ----------------------------------------------------------------------------- -->
  <p class="text-subtitle-1 text-grey-darken-1 mb-6">
    Animations use the application’s $primary-transition.
  </p>
  <v-row justify="center">
    <v-menu transition="slide-y-transition">
      <template #activator="{ props }">
        <v-btn color="primary" class="ma-2" v-bind="props">
          Slide Y Transition
        </v-btn>
      </template>
      <v-list>
        <v-list-item v-for="n in 5" :key="n" link>
          <v-list-item-title>{{ `Item ${n}` }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>

    <div class="mx-4 hidden-sm-and-down"></div>

    <v-menu transition="slide-y-reverse-transition">
      <template #activator="{ props }">
        <v-btn color="secondary" class="ma-2" v-bind="props">
          Slide Y Reverse Transition
        </v-btn>
      </template>
      <v-list>
        <v-list-item v-for="n in 5" :key="n" link>
          <v-list-item-title>{{ `Item ${n}` }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </v-row>
</template>
