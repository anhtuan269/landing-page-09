<template>
  <div class="testimonial mb-10">
      <h3 class=" text-36 leading-l-42 text-black-01 font-medium mb-14">{{item.title}}</h3>
      <img :src="item.url" alt="" class="mx-auto">
      <p class="my-16 w-330 mx-auto leading-l-30 text-black-03 font-medium xl:w-525">{{item.description}}

          <span class="hidden xl:inline-block">{{item.span}}</span>
      </p>
      <div class="auth flex justify-center items-center">
          <img :src="item.avatar" alt="" >
        <div class="posotion text-left ml-5">
              <h5 class="text-18 leading-5 tracking-wide text-black-01 font-medium mb-1 ">{{item.name}}</h5>
          <p class="text-18 leading-7 font-medium ">{{item.position}}</p>
        </div>
      </div>
  </div>
</template>

<script>

export default {
props: {
    item:{
        type:Object
    }
}
}
</script>

<style>

</style>