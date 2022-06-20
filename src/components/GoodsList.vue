<template>
    <div>
      <slot name="header" />
      <div :class="isHeaderSlot ? 'mt-5' : ''">
        <v-row>
          <v-col cols="4">
            <GoodsCard title="asdasd" is-in-cart />
          </v-col>
          <v-col cols="4">
            <GoodsCard />
          </v-col>
          <v-col cols="4">
            <GoodsCard />
          </v-col>
          <v-col cols="4">
            <GoodsCard />
          </v-col>
        </v-row>
      </div>
    </div>
</template>

<script setup lang="ts">
import { useSlots, computed } from 'vue';
import GoodsCard from './GoodsCard.vue';

const slots = useSlots();
const isHeaderSlot = computed(() => slots.header);

</script>
<script lang="ts">
export default {
  name: 'GoodsList',
};
</script>

<style scoped>

</style>
