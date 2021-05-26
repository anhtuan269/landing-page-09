<template>
  <button
  class="rounded-at font-bold leading-5 duration-300 ease-linear focus:outline-none    "
  :class="background"
  >{{item.text}}</button>
</template>

<script>
export default {
    props:{
        item: {
            type:Object
        },
        type: {
            type:String
        }
    },
    computed: {
        background() {
            if( this.type === 'login') {
                return '  bg-white border-primary border text-primary mr-3 hover:text-white hover:bg-primary text-18 px-9 py-4  z-20 md:px-14'
            } else if( this.type==='started'){
                return ' bg-primary text-white border-primary hover:bg-white hover:text-black-01 text-18 px-10 py-4 border hover:border-white z-30 '
            }
            else if( this.type==='try'){
                return ' bg-primary text-white border-primary hover:bg-white hover:text-black-01 text-18 px-10 py-4'
            }
            else if( this.type==='download'){
                return ' bg-primary text-white border-primary border-2 hover:bg-white  text-18 px-10 py-4 mb-5 w-330 mx-auto hover:text-primary md:mb-0  xl:mx-0'
            }
            else if( this.type==='see'){
                return ' bg-primary text-white border-primary hover:bg-white hover:text-primary border-2 text-18 px-10 py-4 w-330 mx-auto xl:mx-0'
            } else if( this.type==='free'){
                return ' bg-primary text-white border-primary hover:bg-white hover:text-primary border-2 text-18 px-10 py-4 w-290 mx-auto'
            }
            else if( this.type==='testimonial'){
                return ' bg-primary text-white border-primary hover:bg-white hover:text-primary border-2 text-18 px-10 py-4 w-250 mx-auto'
            } else {
                return ' bg-primary text-white border-primary hover:bg-white hover:text-primary border-2 text-18 px-10 py-4 w-250 mx-auto'
            }
        }
    }

}
</script>

<style>

</style>