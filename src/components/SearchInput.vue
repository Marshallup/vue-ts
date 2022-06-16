<template>
  <v-form>
    <v-text-field
      class="search-input-class"
      variant="contained"
      dense
      hide-details
      density="compact"
      placeholder="Поиск"
      prepend-inner-icon="mdi-magnify"
      solo
      single-line
      v-bind="$attrs"
    />
  </v-form>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';

// type MyComponentProps = InstanceType<typeof VTextField>;
// console.log(InstanceType<typeof VTextField>);
// console.log(type VTextField, 'v text');
defineProps<{ test?: string }>();

// console.log(MyComponentProps, 'MyComponentProps')
</script>
<script lang="ts">
export default {
  name: 'SearchInput',
  inheritAttrs: false,
};
</script>

<!-- <script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'SearchInput',
});
</script> -->

<style lang="scss" scoped>
.search-input-class {
  :deep(.v-field) {
    border-radius: 10px;
  }
  :deep(.v-field__field) {
    padding-top: 0;
  }
}
</style>
