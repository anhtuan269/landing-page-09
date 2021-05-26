<template>
  <li class="mb-3 hover:text-yellow-01 duration-300 ease-linear">
    <nuxt-link :to="item.link">{{ item.text }}</nuxt-link>
  </li>
</template>

<script>
export default {
    props: {
        item: {
            type: Object
        }
    }
};
</script>

<style>
</style>