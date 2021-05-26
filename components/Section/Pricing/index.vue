<template>
  <div class="pricing bg-black-03 py-100 px-5 text-white text-center">
    <div class="xl:max-w-880 xl:mx-auto xl:flex xl:justify-between">
      <div class="xl:text-left xl:w-420">
        <Heading
          v-for="(head, index) in heading"
          :key="index"
          :head="head"
          :type="head.type"
          v-show="head.type === 'pricing'"
        />
      </div>
      <div class="right">
        <Trial v-for="(item, index) in trial" :item="item" :key="index" />

        <Button
          v-for="(item, index) in button"
          :key="index"
          :item="item"
          :type="item.type"
          v-show="item.type === 'started'"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Trial from "@/components/Trial";
export default {
  components: {
    Heading,
    Trial,
  },
  data() {
    return {
      heading: [],
      trial: [],
      button: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.trial = await fetch("http://localhost:3000/trial").then((res) => {
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