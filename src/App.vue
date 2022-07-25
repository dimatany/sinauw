<template>
  <Header/>
  <Hero/>
  <Featured/>
  <Classes/>
  <Webinar/>
  <Pricing/>
  <Apps/>
  <Footer/>

  <router-view/>

</template>

<script>

import Header from '@/components/header-block'
import Hero from '@/components/hero-block'
import Featured from '@/components/featured-block'
import Classes from '@/components/classes-block'
import Webinar from '@/components/webinar-block'
import Pricing from '@/components/pricing-block'
import Apps from '@/components/apps-block'
import Footer from '@/components/footer-block'


export default {
  components: {
    Header,
    Hero,
    Featured,
    Classes,
    Webinar,
    Pricing,
    Apps,
    Footer,
  }
}
</script>
