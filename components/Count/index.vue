<template>
  <div class="count max-w-330 mx-auto mb-5 md:max-w-480 xl:max-w-700 xl:mb-20">
    <div class="bg w-330 mx-auto relative bg-gray-01 rounded-full h-4 mb-5 md:w-full">
      <div
        class="w-9/12 absolute top-0 bg-primary h-4 left-0 rounded-full"
      ></div>
    </div>

    <div class="flex justify-between">
      <p class="text-14 leading-6 text-black-03 ">{{ item.text }}</p>
      <p class="text-14 leading-6 text-black-04 font-bold">{{ item.count }}</p>
    </div>
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