<template>
  <div
    class="meeting text-center mt-60 overflow-x-hidden mb-20 md:mt-40 xl:max-w-1200 xl:mx-auto xl:flex xl:justify-center xl:items-center xl:mt-52 acer:max-w-1280 xl:overflow-x-visible"
  >
    <div class="xl:w-536 xl:ml-5">
      <Picture
        v-for="(item, index) in image"
        :item="item"
        :key="index"
        v-show="item.type === 'variable'"
        :type="item.type"
      />
    </div>
    <div class="head mt-20 xl:w-460 xl:mt-0 ">
      <div class="variable hidden xl:inline-block xl:text-left acer:ml-20">
        <Heading
          v-for="(head, index) in heading"
          :key="index"
          :head="head"
          :type="head.type"
          v-show="head.type === 'variable'"
        />
      </div>
      <div class="feature xl:hidden">
        <Heading
          v-for="(head, index) in heading"
          :key="index"
          :head="head"
          :type="head.type"
          v-show="head.type === 'feature'"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Picture from "@/components/Picture";
export default {
  components: {
    Heading,
    Picture,
  },
  data() {
    return {
      heading: [],
      image: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });

    this.image = await fetch("http://localhost:3000/imagesss").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>