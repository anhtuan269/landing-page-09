<template>
  <div
    class="header flex items-center justify-between max-w-420 mx-auto mt-10 mb-40 md:max-w-2xl xl:max-w-1200 xl:px-03"
  >
    <Logo
      v-for="(item, index) in headerLogo"
      :key="index"
      :item="item"
      :type="item.type"
    />
    <ul class="hidden xl:flex">
      <Menu v-for="(item, index) in menu" :key="index" :item="item" />
    </ul>
    <div class="right flex justify-between items-center">
      <div class="button md:mr-5">
        <Button
          v-for="(item, index) in button"
          :key="index"
          :item="item"
          v-show="item.type === 'login'"
          :type="item.type"
        />
      </div>
      <div class="menu-icon xl:hidden">
        <Picture
          v-for="(item, index) in image"
          :key="index"
          :item="item"
          v-show="item.type === 'mobile'"
          :type="item.type"
          @menuMobile="change"
        />
      </div>
      <div
        class="fixed top-0 right-0 h-screen w-250 bg-black-01 border border-black-01 text-white p-10 transform duration-300 ease-linear"
        :class="position"
      >
        <ul>
          <li @click="change">
            <img
              src="@/static/image/cancel1.svg"
              alt=""
              class="w-6 ml-auto cursor-pointer bg-white rounded-full"
            />
          </li>
          <Mobile v-for="(item, index) in menu" :key="index" :item="item" />
          <Mobile v-for="(item, index) in menu" :key="index" :item="item" />
          <Mobile v-for="(item, index) in menu" :key="index" :item="item" />
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from "@/components/Logo";
import Menu from "@/components/Menu";
import Mobile from "@/components/Mobile";
import Button from "@/components/Button";
import Picture from "@/components/Picture";
export default {
  components: {
    Logo,
    Button,
    Menu,
    Picture,
    Mobile,
  },
  data() {
    return {
      menu: [],
      logo: [],
      button: [],
      image: [],
      mobile: true,
    };
  },
  async fetch() {
    this.menu = await fetch("http://localhost:3000/menu").then((res) => {
      return res.json();
    });

    this.logo = await fetch("http://localhost:3000/logo").then((res) => {
      return res.json();
    });
    this.button = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
    this.image = await fetch("http://localhost:3000/imagesss").then((res) => {
      return res.json();
    });
  },
  methods: {
    change() {
      return (this.mobile = !this.mobile);
    },
  },
  computed: {
    position() {
      if (this.mobile === true) {
        return "opacity-0 translate-x-2/4 z-a";
      } else {
        return "opacity-100 -translate-x-14 md:-translate-x-24 z-20";
      }
    },
    headerLogo() {
      return this.logo.filter(function (item) {
        return item.type === "header";
      });
    },  
  },
};
</script>

<style>
</style>