<template>
  <div id="app">
    <main>
      <Header v-bind:links="headerLinks" v-bind:changeRoute="changeRoute" />
      <div v-if="route == '/'">
        <Carousel />
        <Temp />
      </div>

      <div v-if="route == '/doctors'">
        <!-- <Doctors v-bind:doctors="doctors" v-bind:isDoctorsLoaded="isDoctorsLoaded" v-bind:filterDoctors="filterDoctors" v-bind:alphabet="alphabet" /> -->
        <Doctors v-bind:apiKey="apiKey" />
      </div>
      <Footer />
    </main>
  </div>
</template>

<script>
import Header from './components/core/Header'
import Carousel from './components/Carousel'
import Temp from './components/Temp'
import Footer from './components/core/Footer'
import Doctors from './components/Doctors'

export default {
  name: 'App',
  components: {
    Header,Carousel,Temp,Footer,Doctors
  },
  data(){
    return {
      apiKey:'eSWHugHzUmZQ2GUsBKffyNKeNZHuSWtX',
      route:window.location.pathname,
      headerLinks:[
        [
          {href:'/',title:'Home',},
          {href:'/mission-vision',title:'Mission Vision',},
        ],
        [
          {href:'/our-services',title:'Our Services',},
          {href:'/wellness',title:'Wellness',},
          {href:'/diagnostic-centers',title:'Diagnostic Centers',},
        ],
        [
          {href:'/doctors',title:'Our Doctors',},
          {href:'/departments',title:'Clinical Department',},
          {href:'/doctor/specialty',title:'Per Doctor / Specialty',},
        ],
      ],
    };
  },
  methods:{
    changeRoute(route){
      this.route = route;
      window.location.pathname = this.route;
    },
  },
}
</script>

<style>
</style>
