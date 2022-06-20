<template>
    <div class="item">
        <div class="title mb-2">
          Цена
        </div>
        <FilterItemButtons />
    </div>
</template>

<script setup lang="ts">
import FilterItemButtons from './FilterItems/FilterItemButtons.vue';

</script>
<script lang="ts">
export default {
  name: 'FilterPanel',
};
</script>

<style lang="scss" scoped>
.item {
  margin-bottom: 20px;
  &:last-child {
    margin-bottom: 0;
  }
}
</style>
