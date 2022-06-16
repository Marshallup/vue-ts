<template>
    <div>
        <router-link class="link" to="/">
            link1
        </router-link>
        <router-link class="link" to="#">
            link2
        </router-link>
    </div>
</template>

<script setup lang="ts">

</script>
<script>
export default {
  name: 'HeaderMenu',
};
</script>

<style lang="scss" scoped>
.link {
  color: white;
  margin-right: 10px;
  text-decoration: none;
  font-size: 18px;

  &:last-child {
    margin-right: 0;
  }
}
</style>
