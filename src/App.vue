<template>
  <v-app>
    <component :is="layoutComponent" />
  </v-app>
</template>

<script lang="ts">
import { defineComponent, computed } from 'vue';
import { useRoute } from 'vue-router';
import MainLayout from '@/layouts/MainLayout.vue';

export default defineComponent({
  components: {
    MainLayout,
  },
  setup() {
    const route = useRoute();

    return {
      layoutComponent: computed(() => route.meta.layout || 'MainLayout'),
    };
  },
});
</script>

<!-- <script lang="ts" setup>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import MainLayout from '@/layouts/MainLayout.vue';

const route = useRoute();
const layoutComponent = computed(() => route.meta.layout || 'MainLayout');

</script> -->
