<template>
  <v-btn-toggle
    v-model="value"
    density="compact"
    class="btn-group"
    color="primary"
    mandatory
  >
    <v-btn
      v-for="btn in values"
      :key="btn.value"
      :value="btn.value"
      :icon="btn.icon"
      class="btn"
    />
  </v-btn-toggle>
</template>

<script lang="ts" setup>
import {
  defineProps,
  defineEmits,
  computed,
} from 'vue';

interface Value {
  value: string,
  icon: string,
}

interface Props {
  modelValue: Value['value'],
  values: Value[],
}
interface Emits {
  (event: 'update:modelValue', value: Props['modelValue']): void,
}
const props = defineProps<Props>();
const emit = defineEmits<Emits>();

const value = computed({
  get: () => props.modelValue,
  set: (val) => emit('update:modelValue', val),
});
</script>

<style lang="scss" scoped>
.btn {
  padding-left: 20px;
  padding-right: 20px;
}
</style>
