<template>
  <div class="mt-40 text-center relative pb-28 overflow-x-hidden">
    <Testimonial
      v-for="(item, index) in testimonial"
      :key="index"
      :item="item"
    />
    <Button
      v-for="(item, index) in button"
      :key="index"
      :item="item"
      v-show="item.type === 'testimonial'"
      :type="item.type"
    />
    <Picture
      v-for="(item, index) in image"
      :item="item"
      :key="index"
      :type="item.type"
      v-show="item.type === 'testimonial'"
    />
  </div>
</template>

<script>
import Testimonial from "@/components/Testimonial";
import Button from "@/components/Button";
import Picture from '@/components/Picture'

export default {
  components: {
    Testimonial,
    Button,
    Picture
  },
  data() {
    return {
      testimonial: [],
      button: [],
      image:[]
    };
  },
  async fetch() {
    this.testimonial = await fetch("http://localhost:3000/tetimonial").then(
      (res) => {
        return res.json();
      }
    );
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