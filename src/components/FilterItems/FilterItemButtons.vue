<template>
  <v-btn-toggle
    color="primary"
    variant="outlined"
    density="compact"
    multiple
  >
    <v-btn class="btn mr-2">
      dasdasd
    </v-btn>
    <v-btn class="btn mr-2">
      dasdasd
    </v-btn>
  </v-btn-toggle>
</template>

<script setup lang="ts">

</script>
<script>
export default {
  name: 'FilterItemButtons',
};
</script>

<style lang="scss" scoped>
.btn {
  border: 1px solid black !important;
  border-radius: 4px !important;
  &:last-child {
    margin-right: 0 !important;
  }
}
</style>
