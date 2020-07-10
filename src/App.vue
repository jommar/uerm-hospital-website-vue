<template>
  <div id="app">
    <main>
      <Header v-bind:links="headerLinks" v-bind:changeRoute="changeRoute" />
      <div v-if="route == '/'">
        <Carousel v-bind:carousel="carousel" />
        <Temp />
      </div>

      <div v-if="route == '/doctors'">
        <Doctors v-bind:doctors="doctors" v-bind:isDoctorsLoaded="isDoctorsLoaded" v-bind:filterDoctors="filterDoctors" v-bind:alphabet="alphabet" />
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
      doctorsAll:[],
      isDoctorsLoaded:false,
      route:window.location.pathname,
      alphabet:['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'],
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

      this.doctorsAll = responseJson.doctors;
      this.doctors = this.doctorsAll;
      this.isDoctorsLoaded = true;
    },
    changeRoute(route){
      this.route = route;
      window.location.pathname = this.route;
    },
    filterDoctors(letter){
      if(letter == ''){
        this.doctors = this.doctorsAll;
        return;
      }
      this.doctors = this.doctorsAll.filter((doctor)=>{return doctor.fullName.substring(0,1) == letter});
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
