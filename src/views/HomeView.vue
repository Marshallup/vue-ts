<template>
  <div>
    <h1 class="mb-3 mt-3 text-h1">Главная</h1>
    <div class="mt-6">
      <v-row>
        <v-col cols="3">
          <FilterPanelVue />
        </v-col>
        <v-col cols="9">
          <GoodsListVue>
            <template #header>
              <GoodsHeader
                v-model:sort-value="sortVal"
                v-model:grid-value="gridVal"
              />
            </template>
          </GoodsListVue>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import FilterPanelVue from '@/components/FilterPanel.vue';
import GoodsListVue from '@/components/GoodsList.vue';
import GoodsHeader from '@/components/GoodsHeader.vue';

const sortVal = ref(undefined);
const gridVal = ref('grid');

</script>
