<template>
  <v-breadcrumbs class="pl-0" :items="items">
    <template #divider>
      <v-icon icon="mdi-chevron-right"></v-icon>
    </template>

    <template #text="{ item }">
      <router-link
        class="v-breadcrumbs-item v-breadcrumbs-item--link"
        :to="item.href"
      >
        {{ item.text }}
      </router-link>
    </template>
  </v-breadcrumbs>
</template>

<script setup lang="ts">
import { reactive } from 'vue';

const items = reactive([
  {
    text: 'Главная',
    disabled: false,
    href: '/',
  },
  {
    text: 'Вторая',
    disabled: false,
    href: '/',
  },
]);
</script>
<script lang="ts">
export default {
  name: 'MainBreadcumbs',
};
</script>

<style scoped>

</style>
