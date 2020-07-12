<template>
  <div id="app">
    <main>
      <Header />

      <div v-if="route == '/'">
        <Carousel />
        <News />
        <Promos />
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
import Footer from './components/core/Footer'
import Doctors from './components/Doctors'
import News from './components/News'
import Promos from './components/Promos'

export default {
  name: 'App',
  components: {
    Header,Carousel,Footer,Doctors,News,Promos
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
