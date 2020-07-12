<template>
  <div class="py-3">
    <div class="container my-3">
      <h2 class="h1 mb-3 text-center">Promos</h2>
      <hr>
      <div class="row">
        <div class="col-lg-6 g-mb-30" v-bind:key="key" v-for="(promo,key) in promos">
          <article class="g-bg-size-cover" v-bind:data-bg-img-src="promo.image">
            <div
              class="w-100 g-min-height-360 g-flex-middle g-width-50x--md g-bg-primary-opacity-0_8 g-pa-25 ml-auto"
            >
              <div class="g-flex-middle-item">
                <h4 class="h5 g-color-white g-font-weight-700 text-uppercase g-mb-10">{{promo.title}}</h4>
                <p
                  class="g-color-white-opacity-0_9 mb-0"
                >{{promo.content}}</p>
              </div>
            </div>
          </article>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      promos: [
        { image: "assets/img-temp/500x450/img4.jpg", title: "Amet cupidatat ut minim", content: "Amet in dolor ut veniam Lorem irure ullamco aliquip aliquip." },
        { image: "assets/img-temp/500x450/img4.jpg", title: "Ut nisi excepteur", content: "Tempor exercitation est tempor aliqua nostrud velit occaecat amet commodo deserunt." },
        { image: "assets/img-temp/500x450/img4.jpg", title: "Adipisicing dolore anim laborum", content: "Pariatur amet sit ad quis minim exercitation ut exercitation voluptate occaecat aute anim.." },
        { image: "assets/img-temp/500x450/img4.jpg", title: "Officia eiusmod", content: "Laborum esse reprehenderit dolor eu laboris nisi consectetur enim exercitation." },
      ]
    };
  }
};
</script>

<style scoped>
</style>