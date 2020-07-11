<template>
  <div id="app">
    <main>
      <Header />

      <div v-if="route == '/'">
        <Carousel />
        <Temp />
      </div>

      <div v-if="route == '/doctors'">
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
    };
  },
  methods:{
  },
}
</script>

<style>
</style>
