<template>
  <div class="trial">
    <h3
      class="text-24 leading-l-38 tracking-wide font-medium mb-4 text-center w-160 mx-auto md:w-full"
    >
      {{ item.title }}
    </h3>
    <p class="flex justify-center items-center">
      <span class="text-72 font-black leading-l-78 text-yellow-01 mr-2 md:mr-0">{{ item.price }}</span>
      <span
        class=" text-18 leading-7 font-medium w-70 md:w-160"
      >
        {{ item.time }}</span
      >
    </p>
    <p class="my-8 w-190 mx-auto  leading-l-30 font-medium md:w-full ">{{ item.description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
  },
};
</script>

<style>
</style>