<!-- eslint-disable @typescript-eslint/no-unused-vars -->
<script setup lang="ts">
import { ref } from 'vue'
const value = ref('Message')
const rules = ref([
  (v: string | any[]) => v.length <= 25 || 'Max 25 characters',
])
</script>

<template>
  <div>
    <v-alert
      icon="mdi-alert-outline"
      outlined
      variant="tonal"
      type="info"
      class="my-2 mb-3 caption pa-3"
      >Form Action at center align of the form</v-alert
    >
    <h6 class="text-subtitle-1 text-grey-darken-1">
      To use add form actions on top of the form add a div with .action-form
      class to the ending of the form. To set a side of the button use
      .text-center as per requirement.
    </h6>
    <v-row class="mt-3">
      <v-col cols="12">
        <v-text-field label="Full Name" variant="outlined"></v-text-field>
        <v-text-field label="Email" variant="outlined"></v-text-field>
        <v-text-field label="Contact no" variant="outlined"></v-text-field>
        <v-text-field label="Donation Type" variant="outlined"></v-text-field>
        <v-textarea
          variant="outlined"
          label="Amount"
          rows="1"
          prepend-inner-icon="mdi-currency-usd"
        ></v-textarea>
        <v-textarea
          variant="outlined"
          label="Comments"
          rows="2"
          :rules="rules"
          counter
        ></v-textarea>
      </v-col>
    </v-row>

    <div class="pa-5 d-flex border-top text-center">
      <v-btn color="primary" class="mr-2 text-capitalize">Save</v-btn>
      <v-btn color="secondary" class="text-capitalize" dark>Cancel</v-btn>
    </div>
  </div>
</template>
