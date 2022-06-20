<template>
    <v-card
        class="mx-auto"
        max-width="400"
    >
        <v-img
          ref="imgRef"
          class="align-end text-white"
          height="200"
          src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          cover
        >
          <div class="controlls" :class="isShowControlls ? 'show' : 'hide'">
            <v-btn
              density="compact"
              color="transparent"
              icon
              class="controlls-item"
            >
              <v-icon :color="inCartColor">mdi-heart</v-icon>
            </v-btn>
          </div>
        </v-img>
        <v-card-subtitle class="pt-3">
            <div>
                12123123 ₽.
            </div>
        </v-card-subtitle>
        <v-card-title>{{ title }}</v-card-title>

        <v-card-actions>
            <v-btn
                variant="contained"
                width="100%"
                color="primary"
            >
                В корзину
            </v-btn>
        </v-card-actions>
    </v-card>
</template>

<script setup lang="ts">
import {
  computed,
  defineProps,
  withDefaults,
  ref,
  onMounted,
  onBeforeUnmount,
  ComponentPublicInstance,
} from 'vue';

interface GoodsCardProps {
  title?: string,
  isInCart?: boolean,
}

const props = withDefaults(defineProps<GoodsCardProps>(), {
  title: 'card title',
});

const imgRef = ref<ComponentPublicInstance | null>(null);
const inCartColor = computed(() => (props.isInCart ? 'pink' : 'white'));
const isShowControlls = ref(false);

function controllsShow() {
  isShowControlls.value = true;
}
function controllsHide() {
  isShowControlls.value = false;
}
function initHandlerControlls(isDestroyListeners = false) {
  if (imgRef.value) {
    const htmlEl = imgRef.value.$el as HTMLDivElement;

    if (!isDestroyListeners) {
      htmlEl.addEventListener('mouseenter', controllsShow);
      htmlEl.addEventListener('mouseleave', controllsHide);
    } else {
      htmlEl.removeEventListener('mouseenter', controllsShow);
      htmlEl.removeEventListener('mouseleave', controllsHide);
    }
  }
}

onMounted(() => {
  initHandlerControlls();
});
onBeforeUnmount(() => {
  initHandlerControlls(true);
});
</script>

<style lang="scss" scoped>
.controlls {
  position: absolute;
  padding: 10px;
  top: 0;
  right: 0;
  transition: transform .3s ease, opacity .3s ease .1s;
  opacity: 1;
  &-item {
    margin-bottom: 10px;
    &:last-child {
      margin-bottom: 0;
    }
  }
}
.hide {
  opacity: 0;
  transform: translateX(100%);
}
</style>
