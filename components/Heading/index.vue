<template>
  <div class="heading  ">
    <h4 :class="name">{{ head.name }}</h4>
    <h3 class="" :class="title">{{ head.title }}</h3>
    <p :class="description">
      {{ head.description }}
      <span class="hidden xl:inline">{{ head.description_2 }}</span>
    </p>
    <p class=" text-18 leading-5 text-primary font-medium hover:text-yellow-01 duration-500 ease-linear cursor-pointer">{{ head.more }}</p>
  </div>
</template>

<script>
export default {
  props: {
    head: {
      type: Object,
    },
    type: {
      type: String,
    },
  },
  computed: {
    title() {
      if (this.type === "hero") {
        return "text-56  leading-l-65 mb-10 text-black-02 font-bold tracking-wide xl:text-72 xl:font-black xl:leading-l-78";
      } else if (this.type === "navigate") {
        return "text-56  leading-l-65 mb-10 text-black-01 font-bold tracking-wide";
      }else if (this.type === "feature") {
        return "text-36  leading-l-42 mb-10 text-black-01 font-medium w-190 mx-auto tracking-wide md:w-full" ;
      }else if (this.type === "variable") {
        return "text-36  leading-l-48 mt-20 mb-10 text-black-01 font-medium tracking-wide  md:w-full xl:mt-0 ";
      }
      else if (this.type === "work") {
        return "text-56  leading-l-65 mb-10 text-black-01 font-bold";
      }
      else if (this.type === "task") {
        return "text-56  leading-l-65 mb-10 text-black-01 font-bold";
      } else if (this.type === "pricing") {
        return "text-56  leading-l-65 mb-6 font-bold tracking-wide";
      }else if (this.type === "metting") {
        return "text-46  leading-l-57 mb-6 font-normal tracking-wide w-310 text-black-01 mx-auto md:w-480 xl:text-36 xl:text-left xl:leading-l-42" ;
      }
    },
    description() {
      if (this.type === "hero") {
        return "text-24 leading-l-38 mb-20  mx-auto xl:w-555";
      } else if(this.type==='navigate') {
        return "text-24 leading-l-38 mb-10 w-330  mx-auto md:w-480";
      }else if(this.type==='feature') {
        return "text-24 leading-l-38 mb-10 w-330  mx-auto md:w-480 xl:w-460 ";
      }else if(this.type==='variable') {
        return "text-24 leading-l-38 mb-10 w-380  mx-auto md:w-480 xl:w-380";
      }else if(this.type==='work') {
        return " font-medium text-black-3 leading-l-30 mb-10 w-330  mx-auto tracking-wide md:w-480 xl:w-full xl:mb-24";
      }else if(this.type==='task') {
        return " font-medium text-black-3 leading-l-30 mb-10 w-330  mx-auto tracking-wide md:w-480 xl:w-full xl:mb-20 ";
      }else if(this.type==='pricing') {
        return " font-medium  leading-l-30 mb-14 w-370  mx-auto tracking-wide md:w-480 xl:w-420";
      }else if(this.type==='metting') {
        return " font-medium  leading-l-30 mb-14 w-370  mx-auto tracking-wide md:w-480 xl: ";
      } else if(this.type==='being') { 
          return ' text-18 text-black-03 leading-l-27 font-normal w-400 mx-auto mb-10 md:w-480'
      } else {
          return 'text-18 text-black-03 leading-l-27 font-normal w-330 mb-10 mx-auto md:w-400 xl:w-480'
      }
    },
    name() {
      if (this.type === "navigate") {
        return "text-36 leading-l-42 text-yellow-01 font-medium mb-10 tracking-wide ";
      } else {
        return "";
      }
    },
  },
};
</script>

<style>
</style>