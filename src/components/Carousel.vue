<template>
    <div>
        <!-- Carousel Slider -->
        <div
            class="js-carousel u-carousel-v5"
            data-infinite="true"
            data-autoplay="true"
            data-speed="8000"
            data-pagi-classes="u-carousel-indicators-v34 g-absolute-centered--y g-left-auto g-right-30 g-right-100--md"
            data-calc-target="#js-header"
        >
            <!-- Carousel Slides -->
            <div
                v-bind:key="item"
                v-for="item in carousel"
                class="js-slide h-100 g-flex-centered g-bg-img-hero g-bg-cover g-bg-black-opacity-0_3--after"
                v-bind:style="{'background-image':item.backgroundImage}"
            >
                <div class="container">
                    <div class="g-max-width-600 g-pos-rel g-z-index-1">
                        <a class="d-block g-text-underline--none--hover" href="#">
                            <span class="d-block g-color-white g-font-size-20--md mb-2">
                                {{item.title}}
                            </span>
                            <span
                                class="d-block g-color-white g-font-secondary g-font-size-25 g-font-size-45--md g-line-height-1_4"
                            >
                                {{item.content}}
                            </span>
                        </a>
                    </div>

                    <!-- Go to Button -->
                    <a
                        class="js-go-to d-flex align-items-center g-color-white g-pos-abs g-bottom-0 g-z-index-1 g-text-underline--none--hover g-pb-60"
                        href="#"
                        data-target="#content"
                    >
                        <span class="d-block u-go-to-v4 mr-3"></span>
                        <span class="g-brd-bottom--dashed g-brd-white-opacity-0_5 mr-1"
                            >scroll down</span
                        >
                        to find out more
                    </a>
                    <!-- End Go to Button -->
                </div>
            </div>
            <!-- End Carousel Slides -->
        </div>
        <!-- End Carousel Slider -->
    </div>
</template>

<script>
export default {
    props:["carousel"]
}
</script>

<style scoped>

</style>