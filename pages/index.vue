<template>
  <div>
    <Header />
    <Slider />
    <Company />
    <Testimonials />
    <Transparent />
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header/Header.vue'
import Slider from '@/components/Slider_Clean/Slider_Clean.vue'
import Company from '@/components/Clean_Company/Company.vue'
import Testimonials from '@/components/Testimonials/Testimonials.vue'
import Transparent from '@/components/Transparent/Transparent.vue'
import Footer from '@/components/Footer/Footer.vue'
export default {
  components: {
    Header,
    Slider,
    Company,
    Testimonials,
    Transparent,
    Footer,
  },
}
</script>
