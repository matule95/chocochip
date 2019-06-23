<template>
  <b-container fluid>
    <b-row>
      <b-col md="1">
        <div id="side-label">
          <span>PHOTOGRAPHY</span>
        </div>
      </b-col>
      <b-col md="10" offset="1">
        <b-row>
          <b-col id="title" md="6">
            <h1>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </h1>
          </b-col>
          <b-col md="6"></b-col>
          <b-col id="description" md="6" class="my-3 text-justify">
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis
              dignissim vehicula feugiat. Proin ac lacinia tellus. Etiam lorem
              turpis, luctus sed augue nec, dictum dapibus tellus. Donec eget
              auctor tellus. Cras fringilla, turpis id laoreet iaculis, tortor
              magna tristique nisi, eget accumsan eros ipsum et lacus. Lorem
              ipsum dolor sit amet, consectetur adipiscing elit. Duis dignissim
              vehicula feugiat. Proin ac lacinia tellus. Etiam lorem turpis,
              luctus sed augue nec, dictum dapibus tellus. Donec eget auctor
              tellus. Cras fringilla, turpis id laoreet iaculis, tortor magna
              tristique nisi, eget accumsan eros ipsum et lacus.
            </p>
          </b-col>
        </b-row>
      </b-col>
      <b-col id="content" md="10" offset="1">
        <b-col md="1"></b-col>
        <b-col lg="10" offset="1">
          <div
            v-masonry
            transition-duration="3s"
            item-selector=".item"
            fit-width
            gutter="10"
            class="masonry-container"
          >
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-01.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-02.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-03.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-04.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-05.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-06.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-01.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-02.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-03.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-04.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-05.jpg" />
            </div>
            <div v-masonry-tile class="item">
              <img class="img-fluid" src="/assets/images/img-06.jpg" />
            </div>
          </div>
        </b-col>
      </b-col>
    </b-row>
    <b-row> </b-row>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      blocks: [
        {
          title: 'nice block'
        },
        {
          title: 'another shiny block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        },
        {
          title: 'the last block'
        }
      ]
    }
  },
  mounted() {
    if (typeof this.$redrawVueMasonry === 'function') {
      this.$redrawVueMasonry()
    }
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
      '.masonry-container .item',
      2,
      {
        delay: 0.5,
        opacity: 0,
        y: -20,
        ease: this.$gsap.Expo.easeInOut
      },
      0.2
    )
  }
}
</script>

<style scoped>
.item {
  width: 300px;
  margin-bottom: 10px;
}

.masonry-container {
  width: 100%;
}
#content {
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE 10+ */
  overflow-y: scroll;
  height: 100vh;
  padding-bottom: 50vh;
  padding-left: 1.5rem;
}
#content::-webkit-scrollbar {
  /* WebKit */
  width: 0;
  height: 0;
}

#side-label {
  position: fixed;
  top: 50%;
  transform: rotate(-90deg);
}
</style>
