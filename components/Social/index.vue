<template>
  <li class="relative group w-10">
    <a href="#" class=" cursor-pointer  group-hover:opacity-0 duration-300 ease-linear w-full " @click.prevent="abc">
      <img
        :src="item.url"
        alt=""
        class=""
      />
    </a>
    <a href="#" class=" absolute top-0 left-0 opacity-0  duration-300 ease-linear group-hover:opacity-100 w-full " @click.prevent="abc">
      <img
        :src="item.url_1"
        alt=""
        class=" w-full"
        
    /></a>
  </li>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
  },
  methods: {
    abc() {},
  },
};
</script>

<style>
</style>