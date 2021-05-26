<template>
    <div class="img " :class="relative" @click="mobile">
        <img :src="item.url" alt=""
        class="duration-300 ease-linear cursor-pointer transform "
        :class="image"
        >
        <img :src="item.url_1" alt=""
        class="cursor-pointer duration-300 ease-linear transform "
        :class="hover"
        >
        <img :src="item.url_2" alt="" class=" z-30" 
        :class="picture"
        />
    </div>
</template>

<script>
export default {
    props: {
        item :{
            type: Object
        },
        type: {
            type:String
        }
    },
    computed: {
        relative() {
            if(this.type==='mobile'){
                return 'relative'
            } else if(this.type==='feature') {
                return 'relative'
            } else if(this.type==='variable') {
                return 'relative'
            } else {
                return ''
            }
        },
        image() {
            if(this.type === 'mobile') {
                return ' hover:opacity-0'
            } else if(this.type==='hero'){
                return ' absolute top-0 -left-2/4 translate-x-2/7 -translate-y-2/7 z-0 md:-left-1/4 z-a xl:left-0 xl:translate-x-0 xl:-translate-y-1/3 xl:top-1/4'
            } else if( this.type==='feature') {
                return 'absolute opacity-0 -right-1/4 z-a xl:opacity-100 -top-1/4 transform translate-y-5 acer:-right-1/4 '
            } else if(this.type==='variable'){
                return 'absolute opacity-0 -left-1/4 xl:opacity-100 z-a -top-2/4 transform translate-y-1/4 acer:-left-1/3 '
            }else if(this.type==='testimonial'){
                return 'absolute top-1/4 -translate-y-full -rotate-90 -left-14 xl:rotate-0 xl:top-2/4 xl:translate-x-full xl:left-20 xl:-translate-y-2/4 '
            }
        },
        hover() {
            if(this.type === 'mobile') {
                return ' opacity-0 absolute top-0 hover:opacity-100'
            } else if(this.type==='hero'){
                return ' absolute bottom-0 -right-2/4 z-a -translate-y-10 md:right-0 md:bottom-1/4 md:translate-y-1/4 xl:bottom-2/4 '
            } else if(this.type==='feature'){
                return ' absolute -left-1/4 top-2/4 transform -translate-y-2/4  z-a xl:opacity-0'
            }else if(this.type==='variable'){
                return ' absolute top-2/4 transform right-0 -translate-y-2/4   z-a xl:opacity-0'
            }else if(this.type==='testimonial'){
                return 'hidden  '
            }
           
        },
        picture() {
            if(this.type === 'feature') {
                return ' max-w-420 mx-auto h-n-400 md:max-w-full  md:h-n-500 xl:max-w-610 xl:h-n-380'
            } else  if(this.type === 'variable') {
                return ' max-w-420 mx-auto h-n- 400 w-full md:max-w-full md:h-n-500 xl:max-w-610 xl:h-n-380'
            }else if(this.type==='testimonial'){
                return 'absolute bottom-0  -right-10 z-a  '
            }else if(this.type==='hero'){
                return 'acer:w-full mx-auto  '
            }
        }
    },
    methods:{
        mobile() {
            this.$emit('menuMobile')
        }
    }

}
</script>

<style>

</style>