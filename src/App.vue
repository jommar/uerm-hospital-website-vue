<template>
  <div id="app">
    <main>
      <Header v-bind:links="headerLinks" />
      <Carousel v-bind:carousel="carousel" />
      <Temp />
      <Footer />
    </main>
  </div>
</template>

<script>
import Header from './components/core/Header'
import Carousel from './components/Carousel'
import Temp from './components/Temp'
import Footer from './components/core/Footer'

export default {
  name: 'App',
  components: {
    Header,Carousel,Temp,Footer
  },
  data(){
    return {
      headerLinks:[
        [
          {href:'#',title:'Home',},
          {href:'#',title:'Mission Vision',},
        ],
        [
          {href:'#',title:'Our Services',},
          {href:'#',title:'Wellness',},
          {href:'#',title:'Diagnostic Centers',},
        ],
        [
          {href:'#',title:'Our Doctors',},
          {href:'#',title:'Clinical Department',},
          {href:'#',title:'Per Doctor / Specialty',},
        ],
      ],
      carousel:[
        {backgroundImage:'url(assets/img-temp/1920x1080/img5.jpg)',title:'Lorem Ipsum',content:'Cras vitae purus sit amet ipsum egestas vestibulum. Nam euismod nisl at magna mattis, quis mattis odio bibendum. Phasellus elementum sodales mauris, at scelerisque mi eleifend efficitur.',},
        {backgroundImage:'url(assets/img-temp/1920x1080/img3.jpg)',title:'Lorem Ipsum',content:'Cras vitae purus sit amet ipsum egestas vestibulum. Nam euismod nisl at magna mattis, quis mattis odio bibendum. Phasellus elementum sodales mauris, at scelerisque mi eleifend efficitur.',},
        {backgroundImage:'url(assets/img-temp/1920x1080/img1.jpg)',title:'Lorem Ipsum',content:'Cras vitae purus sit amet ipsum egestas vestibulum. Nam euismod nisl at magna mattis, quis mattis odio bibendum. Phasellus elementum sodales mauris, at scelerisque mi eleifend efficitur.',},
      ],
    }
  }
}
</script>

<style>
</style>
