<template>
  <div class="logo " >
      <img   :src="item.url" alt="" class="mx-auto xl:mr-auto xl:mx-0">
      <p class="text-18 leading-7 font-medium text-black-03 xl:text-left">{{item.description}}</p>
  </div>
</template>

<script>
export default {
    props:{
        item:{
        type:Object     
        }
    },
    

}
</script>

<style>

</style>