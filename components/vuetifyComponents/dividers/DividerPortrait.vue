<script setup lang="ts">
import { ref } from 'vue'

const items = ref([
  {
    header: 'Today',
  },
  { divider: true },
  {
    avatar: 'https://picsum.photos/250/300?image=660',
    title: 'Meeting @ Noon',
    subtitle: `<span class="font-weight-bold">Spike Lee</span> &mdash; I'll be in your neighborhood`,
  },
  {
    avatar: 'https://picsum.photos/250/300?image=821',
    title: 'Summer BBQ <span class="grey--text text--lighten-1"></span>',
    subtitle:
      '<span class="font-weight-bold">to Operations support</span> &mdash; Wish I could come.',
  },
  {
    avatar: 'https://picsum.photos/250/300?image=783',
    title: 'Yes yes',
    subtitle:
      '<span class="font-weight-bold">Bella</span> &mdash; Do you have Paris recommendations',
  },
  {
    header: 'Yesterday',
  },
  { divider: true },
  {
    avatar: 'https://picsum.photos/250/300?image=1006',
    title: 'Dinner tonight?',
    subtitle:
      '<span class="font-weight-bold">LaToya</span> &mdash; Do you want to hang out?',
  },
  {
    avatar: 'https://picsum.photos/250/300?image=146',
    title: 'So long',
    subtitle:
      '<span class="font-weight-bold">Nancy</span> &mdash; Do you see what time it is?',
  },
  {
    header: 'Last Week',
  },
  { divider: true },
  {
    avatar: 'https://picsum.photos/250/300?image=1008',
    title: 'Breakfast?',
    subtitle:
      '<span class="font-weight-bold">LaToya</span> &mdash; Do you want to hang out?',
  },
  {
    avatar: 'https://picsum.photos/250/300?image=839',
    title: 'Winter Porridge <span class="grey--text text--lighten-1"></span>',
    subtitle:
      '<span class="font-weight-bold">cc: Daniel</span> &mdash; Tell me more...',
  },
  {
    avatar: 'https://picsum.photos/250/300?image=145',
    title: 'Oui oui',
    subtitle:
      '<span class="font-weight-bold">Nancy</span> &mdash; Do you see what time it is?',
  },
])
</script>

<template>
  <!-- ----------------------------------------------------------------------------- -->
  <!-- Portrait -->
  <!-- ----------------------------------------------------------------------------- -->
  <div>
    <p class="text-subtitle-1 text-grey-darken-1">
      Create custom cards to fit any use-case
    </p>
    <div class="mt-4">
      <v-row justify="center">
        <v-col cols="12">
          <v-card>
            <v-toolbar color="orange-lighten-1">
              <v-app-bar-nav-icon color="black"></v-app-bar-nav-icon>

              <v-toolbar-title>Message Board</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon color="black">
                <v-icon>mdi-magnify</v-icon>
              </v-btn>
            </v-toolbar>

            <v-list lines="two">
              <template v-for="(item, index) in items">
                <v-list-subheader v-if="item.header" :key="item.header" inset>
                  {{ item.header }}
                </v-list-subheader>

                <v-divider
                  v-else-if="item.divider"
                  :key="index"
                  inset
                ></v-divider>

                <v-list-item
                  v-else
                  :key="item.title"
                  :prepend-avatar="item.avatar"
                  ripple
                >
                  <template #title>
                    <div v-html="item.title"></div>
                  </template>
                  <template #subtitle>
                    <div v-html="item.subtitle"></div>
                  </template>
                </v-list-item>
              </template>
            </v-list>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </div>
</template>
