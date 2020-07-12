<template>
  <div class="g-bg-main-light-v2 py-3">
    <div class="container my-3">
      <h2 class="h1 mb-3 text-center g-color-white">News and Announcements</h2>
      <hr class="bg-white">
      <div class="row">
        <div class="col-md-6 col-lg-4 g-mb-20" v-for="(news,key) in news" v-bind:key="key">
          <article class="media g-mb-20">
            <a class="d-flex mr-3" v-bind:href="news.url">
              <img class="g-width-120 g-height-70" v-bind:src="news.image" v-bind:alt="news.title" />
            </a>

            <div class="media-body">
              <h3 class="h6">
                <a class="g-color-main g-color-primary--hover g-color-white" href="#">{{news.title}}</a>
              </h3>

              <ul class="u-list-inline g-font-size-12 g-color-gray-dark-v4">
                <li class="list-inline-item g-color-white">{{news.date}}</li>
              </ul>
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
      news: [
        {
          title:
            "Anim amet voluptate exercitation laborum aliqua sit minim veniam.",
          date: "July 18, 2017",
          url: "#",
          image: "assets/img-temp/140x80/img1.jpg"
        },
        {
          title:
            "Labore exercitation nisi id ipsum adipisicing laboris aliquip sint cillum officia.",
          date: "July 18, 2017",
          url: "#",
          image: "assets/img-temp/140x80/img1.jpg"
        },
        {
          title:
            "Excepteur excepteur tempor consectetur ea ad mollit proident.",
          date: "July 18, 2017",
          url: "#",
          image: "assets/img-temp/140x80/img1.jpg"
        },
        {
          title: "Dolor id enim fugiat aute culpa.",
          date: "July 18, 2017",
          url: "#",
          image: "assets/img-temp/140x80/img1.jpg"
        },
        {
          title:
            "Esse nulla cupidatat deserunt reprehenderit non in ullamco cillum ea.",
          date: "July 18, 2017",
          url: "#",
          image: "assets/img-temp/140x80/img1.jpg"
        },
        {
          title:
            "Fugiat adipisicing dolore labore aute amet nostrud aute fugiat et incididunt labore.",
          date: "July 18, 2017",
          url: "#",
          image: "assets/img-temp/140x80/img1.jpg"
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>