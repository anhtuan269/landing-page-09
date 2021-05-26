<template>
  <div class="navigate max-w-400 mx-auto text-center mb-20 md:max-w-2xl">
    <Heading
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      :type="head.type"
      v-show="head.type === 'navigate'"
    />
    <div class="flex flex-col md:flex-row md:justify-between xl:w-480 xl:mx-auto">
      <Button
        class="md:w-5/12 "
        v-for="(item, index) in button"
        :item="item"
        :key="index"
        v-show="item.type === 'download'"
        :type="item.type"
      />
      <Button
        class="md:w-5/12 xl:w-6/12"
        v-for="(item, index) in button"
        :item="item"
        :key="index"
        :type="item.type"
        v-show="item.type === 'see'"
      />
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