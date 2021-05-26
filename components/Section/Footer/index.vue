<template>
  <div class="footer max-w-400 mx-auto text-center pb-20 md:max-w-xl xl:max-w-1200 xl:flex xl:justify-between xl:items-center acer:max-w-1280">
    <Logo v-for="(item, index) in logo" :key="index" :item="item" v-show="item.type==='footer'" />
   <div class="md:flex md:justify-between md:items-center xl:w-8/12 ">
      <ul class="menu mt-20 flex flex-col md:flex-row md:justify-center md:mt-10 ">
      <Menu v-for="(item, index) in menu" :key="index" :item="item" />
    </ul>
    <ul class="social flex justify-between w-200 mx-auto mt-5 items-center md:mt-10 md:w-190 xl:w-250 xl:mx-0 xl:ml-auto" >
      <Social v-for="(item, index) in social" :key="index" :item="item" :type="item.type"  />
    </ul>
   </div>
  </div>
</template>

<script>
import Logo from "@/components/Logo";
import Menu from "@/components/Menu";
import Social from "@/components/Social";
export default {
  components: {
    Logo,
    Menu,
    Social,
  },
  data() {
    return {
      logo: [],
      menu: [],
      social: [],
    };
  },
  async fetch() {
    this.logo = await fetch("http://localhost:3000/logo").then((res) => {
      return res.json();
    });
    this.menu = await fetch("http://localhost:3000/menu").then((res) => {
      return res.json();
    });
    this.social = await fetch("http://localhost:3000/social").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>