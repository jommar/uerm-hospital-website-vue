<template>
  <div>
    <!-- Footer -->
    <footer class="g-bg-secondary g-pt-100 g-pb-50">
      <div class="container">
        <!-- Footer Copyright -->
        <div class="row justify-content-lg-center align-items-center text-center">
          <div class="col-sm-6 col-md-4 col-lg-3 order-md-3 g-mb-30">
            <a class="u-link-v5 g-color-text g-color-primary--hover" href="#">
              <i class="align-middle mr-2 icon-real-estate-027 u-line-icon-pro"></i>
              64 Barangay Do&ntilde;a Imelda, Aurora Boulevard, Quezon City, Philippines
            </a>
          </div>

          <div class="col-sm-6 col-md-4 col-lg-3 order-md-2 g-mb-30">
            <!-- Social Icons -->
            <ul class="list-inline mb-0">
              <li class="list-inline-item g-mx-2">
                <a
                  class="u-icon-v1 u-icon-size--sm u-shadow-v32 g-color-primary g-color-white--hover g-bg-white g-bg-primary--hover rounded-circle"
                  href="https://twitter.com/UERMOfficial"
                  target="_blank"
                >
                  <i class="g-font-size-default fa fa-twitter"></i>
                </a>
              </li>
              <li class="list-inline-item g-mx-2">
                <a
                  class="u-icon-v1 u-icon-size--sm u-shadow-v32 g-color-primary g-color-white--hover g-bg-white g-bg-primary--hover rounded-circle"
                  href="https://facebook.com/UERMOfficial"
                  target="_blank"
                >
                  <i class="g-font-size-default fa fa-facebook"></i>
                </a>
              </li>
              <li class="list-inline-item g-mx-2">
                <a
                  class="u-icon-v1 u-icon-size--sm u-shadow-v32 g-color-primary g-color-white--hover g-bg-white g-bg-primary--hover rounded-circle"
                  href="#"
                >
                  <i class="g-font-size-default fa fa-instagram"></i>
                </a>
              </li>
              <li class="list-inline-item g-mx-2">
                <a
                  class="u-icon-v1 u-icon-size--sm u-shadow-v32 g-color-primary g-color-white--hover g-bg-white g-bg-primary--hover rounded-circle"
                  href="#"
                >
                  <i class="g-font-size-default fa fa-youtube"></i>
                </a>
              </li>
              <li class="list-inline-item g-mx-2">
                <a
                  class="u-icon-v1 u-icon-size--sm u-shadow-v32 g-color-primary g-color-white--hover g-bg-white g-bg-primary--hover rounded-circle"
                  href="#"
                >
                  <i class="g-font-size-default fa fa-linkedin"></i>
                </a>
              </li>
            </ul>
            <!-- End Social Icons -->
          </div>

          <div class="col-md-4 col-lg-3 order-md-1 g-mb-30">
            <p
              class="g-color-text mb-0"
            >University of the East Ramon Magsaysay Medical Center - Since 1956</p>
            <p class="g-color-text mb-0">
              <i class="g-font-size-default fa fa-phone"></i> 8-715-0861 to 77
            </p>
          </div>
        </div>
        <!-- End Footer Copyright -->
        <div class="row text-center">
          <div class="col-6 col-md-4" v-bind:key="key" v-for="(nav, key) in navs">
            <a v-bind:href="nav.url">{{nav.title}}</a>
          </div>
        </div>
      </div>
    </footer>
    <!-- End Footer -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      navs: [
        { url: "/", title: "Home" },
        { url: "/wellness", title: "Welness" },
        { url: "/doctors", title: "Doctors" }
      ]
    };
  }
};
</script>

<style scoped>
</style>