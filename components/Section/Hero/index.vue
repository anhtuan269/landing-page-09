<template>
  <div class="hero  text-center relative  pb-20 overflow-x-hidden bg-gradient-to-b from-blue-02 via-blue-01 to-white-01 z-10 ">
   <div class="h max-w-400 mx-auto  xl:max-w-2xl">
      <Heading
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      :type="head.type"
      v-show="head.type === 'hero'"
    />
   </div>
  <div class="button mb-10 flex justify-between max-w-400 mx-auto xl:mb-0">
      <Button
      v-for="(item, index) in button"
      :item="item"
      :key="index"
      v-show="item.type === 'started'"
      :type="item.type"
    />
    <Button
      v-for="(item, index) in button"
      :item="item"
      :key="index"
      v-show="item.type === 'try'"
      :type="item.type"

    />
  </div>
    <div >
      <Picture
      v-for="(item, index) in image"
      :key="index"
      :item="item"
      v-show="item.type === 'hero'"
      :type="item.type"
      class=""
    />
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Button from "@/components/Button";
import Picture from "@/components/Picture";
export default {
  components: {
    Heading,
    Button,
    Picture,
  },
  data() {
    return {
      heading: [],
      button: [],
      image: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.button = await fetch("http://localhost:3000/button").then((res) => {
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