<template>
  <div id="landing-09">
   <Head />
    <Navigate />
    <Feature />
    <Variable />
    <Work />
    <Testimonial />
    <Pricing />
    <Focus />
    <Footer />
  </div>
</template>

<script>
import Head from '@/components/Section/Head'
import Navigate from "@/components/Section/Navigate";
import Feature from "@/components/Section/Feature";
import Variable from "@/components/Section/Variable";
import Work from "@/components/Section/Work";
import Testimonial from "@/components/Section/Testimonial";
import Pricing from "@/components/Section/Pricing";
import Focus from "@/components/Section/Focus";
import Footer from "@/components/Section/Footer";
export default {
  components: {
    Head,
    Navigate,
    Feature,
    Variable,
    Work,
    Testimonial,
    Pricing,
    Focus,
    Footer,
  },
};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

</style>
