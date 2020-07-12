<template>
  <div class="py-3">
    <div class="container">
      <h2 class="h1 text-center">Wellness Center</h2>
      <hr />
    </div>
    <div class="py-3 my-3 g-bg-main">
      <div class="container">
        <div class="row">
          <div class="col-md-10">
            <div
              id="carousel-09-1"
              class="js-carousel text-center g-font-size-0 g-mb-20 g-mb-0--sm"
              data-infinite="true"
              data-vertical="true"
              data-arrows-classes="u-arrow-v1 g-absolute-centered--x g-width-35 g-height-35 g-font-size-18 g-color-gray g-bg-white"
              data-arrow-left-classes="fa fa-angle-up g-top-0"
              data-arrow-right-classes="fa fa-angle-down g-bottom-0"
              data-nav-for="#carousel-09-2"
            >
              <div class="js-slide" v-bind:key="key" v-for="(image,key) in images">
                <a
                  class="js-fancybox d-block g-pos-rel"
                  href="javascript:;"
                  data-fancybox="lightbox-gallery--09-1"
                  data-src="assets/img-temp/900x600/img3.jpg"
                  data-caption="Welness Center"
                >
                  <img class="img-fluid w-100" v-bind:src="image.src" alt="Image Description" />
                </a>
              </div>
            </div>
          </div>

          <div class="d-none d-md-block col-md-2">
            <div
              id="carousel-09-2"
              class="js-carousel text-center u-carousel-v3 g-mx-minus-10 g-mx-minus-0--sm g-my-minus-5--sm"
              data-infinite="true"
              data-center-mode="true"
              data-vertical="true"
              data-slides-show="4"
              data-is-thumbs="true"
              data-nav-for="#carousel-09-1"
            >
              <div
                class="js-slide g-px-10 g-px-0--sm g-py-5--sm"
                v-bind:key="key"
                v-for="(image,key) in images"
              >
                <img class="img-fluid w-100" v-bind:src="image.src" alt="Image Description" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="container">
      <p class="lead">Ipsum incididunt ex occaecat enim in. Cupidatat officia commodo sunt occaecat exercitation fugiat dolore voluptate officia. Exercitation ipsum ut culpa enim mollit labore deserunt ullamco. Tempor ullamco id id officia ipsum velit eu qui commodo quis in pariatur aute dolor. Commodo anim cillum ex elit cupidatat esse in. Sunt magna consectetur non eiusmod proident dolor est non esse Lorem consequat exercitation velit.</p>
      <p class="lead">Dolore occaecat est labore labore occaecat et proident sint nostrud ut non enim exercitation magna. Incididunt duis officia dolore aliqua ullamco esse incididunt consequat ea in non. Voluptate Lorem ex ex aute ut eu. Fugiat incididunt id consectetur fugiat aliqua nisi. Non magna nulla proident reprehenderit duis qui sit amet.</p>
      <p class="lead">Do pariatur proident officia minim sunt reprehenderit labore tempor laborum deserunt officia pariatur ex proident. Dolore excepteur est fugiat in sint eiusmod. Culpa excepteur labore culpa id anim officia sint consequat duis ut duis.</p>
    </div>
  </div>
</template>

<script>
// import $ from 'jquery';
export default {
  data() {
    return {
      images: [
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" },
        { src: "assets/img-temp/900x600/img3.jpg" }
      ]
    };
  },
  mounted: {
    function() {
      //   $(document).on("ready", function() {
      //     // initialization of popups
      //     $.HSCore.components.HSPopup.init(".js-fancybox");
      //     // initialization of carousel
      //     $.HSCore.components.HSCarousel.init(".js-carousel");
      //   });
    }
  }
};
</script>

<style scoped>
</style>