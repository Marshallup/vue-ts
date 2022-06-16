<template>
  <v-app-bar absolute extended color="primary">
    <v-container class="pt-0 pb-0 mb-2 fill-height">
      <v-row
        class="ma-0 row-app-bar"
        align="center"
        justify="space-between"
      >
        <div class="mt-2 mr-5">
          <LogoIcon />
        </div>
        <div class="search-input-block flex-grow-1 mr-auto">
          <SearchInput />
        </div>
        <div>
          <HeaderControlls />
        </div>
      </v-row>
    </v-container>
    <template #extension>
      <v-container>
        <div class="d-flex align-center">
          <div class="mr-7">
            <v-btn
              color="white"
              variant="contained"
              prepend-icon="mdi-menu"
            >
              Каталог
            </v-btn>
          </div>
          <div>
            <HeaderMenu />
          </div>
        </div>
      </v-container>
    </template>
  </v-app-bar>

  <v-main>
    <v-container>
      <MainBreadcrumbs />

    <router-view />

    </v-container>
  </v-main>

  <v-footer>
    <v-container>
      <div>v-footer</div>
    </v-container>
  </v-footer>
</template>

<script lang="ts" setup>
import LogoIcon from '@/components/Icons/LogoIcon.vue';
import SearchInput from '@/components/SearchInput.vue';
import HeaderControlls from '@/components/HeaderControlls.vue';
import HeaderMenu from '@/components/HeaderMenu.vue';
import MainBreadcrumbs from '@/components/MainBreadcrumbs.vue';

</script>
<script lang="ts">
export default {
  name: 'MainLayout',
};
</script>

<style lang="scss" scoped>
.search-input-block {
  max-width: 600px;
}
.row-app-bar {
  margin-top: -4px !important;
}
</style>
