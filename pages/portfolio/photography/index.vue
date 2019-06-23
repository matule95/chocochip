<template>
  <b-container fluid>
    <b-row>
      <b-col md="1">
        <filters></filters>
      </b-col>
      <b-col md="10" offset="1">
        <b-row>
          <b-col id="title" md="12">
            <h1>
              PHOTOGRAPHY
            </h1>
          </b-col>
          <b-col id="description" md="10" class="my-3">
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis
              dignissim vehicula feugiat. Proin ac lacinia tellus. Etiam lorem
              turpis, luctus sed augue nec, dictum dapibus tellus. Donec eget
              auctor tellus. Cras fringilla, turpis id laoreet iaculis, tortor
              magna tristique nisi, eget accumsan eros ipsum et lacus.
            </p>
          </b-col>
          <b-col id="content" md="10">
            <b-row class="mt-3 cards">
              <b-col
                v-for="(image, index) of images"
                :key="index"
                lg="4"
                xl="3"
              >
                <info-card
                  :src="image"
                  :index="index"
                  @clicked="gotoPage(index)"
                ></info-card>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Filters from '~/components/Filters'
import InfoCard from '~/components/InfoCard'
export default {
  components: {
    Filters,
    InfoCard
  },
  data: () => ({
    images: [
      '/assets/images/img-01.jpg',
      '/assets/images/img-02.jpg',
      '/assets/images/img-03.jpg',
      '/assets/images/img-04.jpg',
      '/assets/images/img-05.jpg',
      '/assets/images/img-06.jpg',
      '/assets/images/img-07.jpg',
      '/assets/images/img-08.jpg',
      '/assets/images/img-01.jpg',
      '/assets/images/img-02.jpg',
      '/assets/images/img-03.jpg',
      '/assets/images/img-04.jpg',
      '/assets/images/img-05.jpg',
      '/assets/images/img-06.jpg',
      '/assets/images/img-07.jpg',
      '/assets/images/img-08.jpg'
    ],
    selected: true
  }),
  mounted() {
    this.$gsap.TweenMax.from('#title', 1, {
      opacity: 0,
      y: 20,
      ease: this.$gsap.Expo.easeInOut
    })
    this.$gsap.TweenMax.from('#description', 2, {
      opacity: 0,
      y: 20,
      ease: this.$gsap.Expo.easeInOut
    })
    this.$gsap.TweenMax.staggerFrom(
      '.cards .col-lg-4',
      2,
      {
        delay: 0.5,
        opacity: 0,
        y: 20,
        ease: this.$gsap.Expo.easeInOut
      },
      0.2
    )
  },
  methods: {
    gotoPage(index) {
      this.$nextTick(function() {
        this.$gsap.TweenMax.staggerTo('.not-selected', 1.5, {
          opacity: 0,
          ease: this.$gsap.Expo.easeInOut,
          onComplete: () => {
            this.$router.push({
              path: `/portfolio/photography/${index}`,
              params: { id: index }
            })
          }
        })
      })
    }
  }
}
</script>

<style scoped>
#content {
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE 10+ */
  overflow-y: scroll;
  height: 100vh;
  padding-bottom: 300px;
  padding-left: 1.5rem;
}
#content::-webkit-scrollbar {
  /* WebKit */
  width: 0;
  height: 0;
}
</style>
