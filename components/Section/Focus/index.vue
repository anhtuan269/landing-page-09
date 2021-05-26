<template>
  <div class="metting py-05 px-5 bg-gradient-to-b from-blue-04 to-blue-03  text-center mb-10">
    <div class="xl:max-w-880 mx-auto xl:flex xl:justify-between">
      <Heading
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      :type="head.type"
      v-show="head.type === 'metting'"
    />
 <div class="xl:text-left">
      <Heading
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      :type="head.type"
      v-show="head.type === 'being'"
    />
    <Heading
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      :type="head.type"
      v-show="head.type === 'building'"
    />

    <Button
      v-for="(item, index) in button"
      :item="item"
      :key="index"
      v-show="item.type === 'metting'"
      :type="item.type"
    />
 </div>
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Button from "@/components/Button";
export default {
  components: {
    Heading,
    Button,
  },
  data() {
    return {
      heading: [],
      button: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.button = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>