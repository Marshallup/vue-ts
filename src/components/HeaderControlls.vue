<template>
  <div class="d-flex">
    <div>
      <v-btn
        :icon="isLoginIcon"
        @click="toggleIsLogin"
      />
    </div>
    <div>
      <v-badge
        content="3"
        color="error"
        offset-x="10"
        offset-y="12"
      >
        <v-btn icon="mdi-cart" />
      </v-badge>
    </div>
    <div>
      <v-badge
        content="3"
        color="error"
        offset-x="10"
        offset-y="12"
      >
        <v-btn icon="mdi-star" />
      </v-badge>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed, unref } from 'vue';

const isLogin = ref(false);
const isLoginIcon = computed(() => (unref(isLogin) ? 'mdi-account-circle' : 'mdi-login'));

function toggleIsLogin() {
  isLogin.value = !isLogin.value;
}

</script>
<script lang="ts">
export default {
  name: 'HeaderControlls',
};
</script>

<style lang="scss" scoped>

</style>
