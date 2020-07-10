<template>
  <div id="app">
    <main>
      <Header v-bind:links="headerLinks" v-bind:changeRoute="changeRoute" />
      <div v-if="route == '/'">
        <Carousel v-bind:carousel="carousel" />
        <Temp />
      </div>

      <div v-if="route == '/doctors' && doctors.length > 0">
        <Doctors v-bind:doctors="doctors" />
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
      doctors:[],
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
      carousel:[
        {backgroundImage:'url(assets/img-temp/1920x1080/img5.jpg)',title:'Lorem Ipsum',content:'Cras vitae purus sit amet ipsum egestas vestibulum. Nam euismod nisl at magna mattis, quis mattis odio bibendum. Phasellus elementum sodales mauris, at scelerisque mi eleifend efficitur.',},
        {backgroundImage:'url(assets/img-temp/1920x1080/img3.jpg)',title:'Lorem Ipsum',content:'Cras vitae purus sit amet ipsum egestas vestibulum. Nam euismod nisl at magna mattis, quis mattis odio bibendum. Phasellus elementum sodales mauris, at scelerisque mi eleifend efficitur.',},
        {backgroundImage:'url(assets/img-temp/1920x1080/img1.jpg)',title:'Lorem Ipsum',content:'Cras vitae purus sit amet ipsum egestas vestibulum. Nam euismod nisl at magna mattis, quis mattis odio bibendum. Phasellus elementum sodales mauris, at scelerisque mi eleifend efficitur.',},
      ],
    };
  },
  methods:{
    async fetchDoctors(){
      const url = `https://apps.uerm.edu.ph:3443/doctors?auth=${this.apiKey}`;
      const response = await fetch(
        url,
        {method:'GET'}
      );
      const responseJson = await response.json();

      this.doctors = responseJson.doctors;
    },
    changeRoute(route){
      this.route = route;
      window.location.pathname = this.route;
    },
  },
  mounted(){
    // this.fetchDoctors();
    switch(this.route){
      case '/doctors':
        this.fetchDoctors();
        break;
    }
    console.log(this.route);
  }
}
</script>

<style>
</style>
