<template>
  <div class="d-flex align-center justify-space-between">
    <div class="mr-2">
      <v-select
        v-model="valueSort"
        variant="outlined"
        dense
        density="compact"
        class="select"
        :items="sortOptions"
        hide-details
        no-data-text="Нет значений"
      />
    </div>
    <div>
      <GoodsToggleBtn
        v-model="valueGrid"
        :values="gridOptions"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import {
  withDefaults,
  defineProps,
  defineEmits,
  computed,
} from 'vue';
import GoodsToggleBtn from '@/components/GoodsToggleBtn.vue';

type ValueType = { title: string, value: string };
type GridValue = { value: string, icon: string };

interface GoodsHeaderProps {
  sortValue: ValueType | undefined,
  sortOptions?: ValueType[],
  gridValue: GridValue['value'],
  gridOptions?: GridValue[],
}
interface GoodsHeaderEmits {
  (e: 'update:sortValue', value: GoodsHeaderProps['sortValue']): void,
  (e: 'update:gridValue', value: GoodsHeaderProps['gridValue']): void,
}

const props = withDefaults(defineProps<GoodsHeaderProps>(), {
  sortOptions: () => [],
  sortValue: () => ({ title: 'test title', value: 'test value' }),
  gridValue: () => 'grid',
  gridOptions: () => ([
    {
      value: 'grid',
      icon: 'mdi-view-grid',
    },
    {
      value: 'column',
      icon: 'mdi-view-column',
    },
  ]),
});
const emits = defineEmits<GoodsHeaderEmits>();

const valueSort = computed({
  get: () => props.sortValue,
  set: (val) => emits('update:sortValue', val),
});
const valueGrid = computed({
  get: () => props.gridValue,
  set: (val) => emits('update:gridValue', val),
});

</script>
<script lang="ts">
export default {
  name: 'GoodsHeader',
};
</script>

<style lang="scss" scoped>
.select {
  min-width: 200px;
}
</style>
