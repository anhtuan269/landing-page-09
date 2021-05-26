<template>
  <div class="feature mx-auto flex flex-col-reverse items-center  justify-center xl:max-w-1200 mt-60 mb-20 text-center md:mt-40 md:mb-0 xl:flex-row acer:max-w-1280">
    <div class="h">
      <div class="feature hidden xl:inline-block xl:w-450 xl:text-left xl:mr-10">
        <Heading
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        :type="head.type"
        v-show="head.type === 'feature'"
      />
      </div>
     <div class="variable xl:hidden">
        <Heading
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        :type="head.type"
        v-show="head.type === 'variable'"
      />
     </div>
    </div>
    <div class="xl:w-536 acer:ml-20 ">
      <Picture
        v-for="(item, index) in image"
        :item="item"
        :key="index"
        v-show="item.type === 'feature'"
        :type="item.type"
      />
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