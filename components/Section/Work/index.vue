<template>
  <div class="work mt-40 text-center ">
    <div class="head">
      <div class=" hidden xl:inline-block">
        <Heading
          v-for="(head, index) in heading"
          :key="index"
          :head="head"
          :type="head.type"
          v-show="head.type === 'work'"
        />
      </div>
      <div class="task xl:hidden">
        <Heading
          v-for="(head, index) in heading"
          :key="index"
          :head="head"
          :type="head.type"
          v-show="head.type === 'task'"
        />
      </div>
    </div>
    <Count v-for="(item, index) in count" :item="item" :key="index" />
    <Button
      v-for="(item, index) in button"
      :item="item"
      :key="index"
      v-show="item.type === 'free'"
      :type="item.type"
    />
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Button from "@/components/Button";
import Count from "@/components/Count";
export default {
  components: {
    Heading,
    Button,
    Count,
  },
  data() {
    return {
      heading: [],
      button: [],
      count: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.button = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
    this.count = await fetch("http://localhost:3000/count").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>