<script setup lang="ts">
import { ref } from 'vue'
const menu = ref(false)
</script>

<template>
  <!-- ----------------------------------------------------------------------------- -->
  <!-- Expandable -->
  <!-- ----------------------------------------------------------------------------- -->
  <v-card class="pa-4">
    <v-row class="px-6 py-3" align="center">
      <span class="mr-4">To</span>
      <v-menu
        v-model="menu"
        location="bottom end"
        transition="scale-transition"
        origin="top left"
      >
        <template #activator="{ on }">
          <v-chip pill class="mb-3" v-on="on">
            <v-avatar start>
              <v-img src="https://cdn.vuetifyjs.com/images/john.png"></v-img>
            </v-avatar>
            John Leider
          </v-chip>
        </template>
        <v-card width="300">
          <v-list dark>
            <v-list-item>
              <v-avatar>
                <v-img src="https://cdn.vuetifyjs.com/images/john.png"></v-img>
              </v-avatar>
              <v-list-item-content>
                <v-list-item-title>John Leider</v-list-item-title>
                <v-list-item-subtitle>john@vuetifyjs.com</v-list-item-subtitle>
              </v-list-item-content>
              <v-list-item-action>
                <v-btn icon @click="menu = false">
                  <v-icon>mdi-close-circle</v-icon>
                </v-btn>
              </v-list-item-action>
            </v-list-item>
          </v-list>
          <v-list>
            <v-list-item @click="() => {}">
              <v-list-item-action>
                <v-icon>mdi-briefcase</v-icon>
              </v-list-item-action>
              <v-list-item-subtitle>john@gmail.com</v-list-item-subtitle>
            </v-list-item>
          </v-list>
        </v-card>
      </v-menu>
    </v-row>

    <v-divider></v-divider>

    <v-text-field
      full-width
      model-value="Re: Vacation Request"
      label="Subject"
      single-line
    ></v-text-field>

    <v-textarea full-width single-line label="Message"></v-textarea>
  </v-card>
</template>
