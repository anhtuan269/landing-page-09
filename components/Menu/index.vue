<template>
  <li class="mb-5 text-black-01 font-medium leading-l-5 hover:text-primary duration-300 ease-linear md:mb-0 md:ml-5 xl:ml-8">
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