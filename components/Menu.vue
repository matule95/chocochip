<template>
  <div class="menu">
    <b-row id="menu" class="menu-wrapper">
      <b-col class="pt-5">
        <img
          class="img-fluid menu-button"
          src="/assets/icons/menu.svg"
          @click="toggle"
        />
      </b-col>
      <b-col md="12" align-self="center">
        <b-row align-v="center" class="social">
          <b-col md="12">
            <img
              id="instagram"
              class="icon"
              src="/assets/icons/instagram.svg"
            />
          </b-col>
          <b-col md="12" class="mt-4">
            <img class="icon" src="/assets/icons/twitter.svg" />
          </b-col>
          <b-col md="12" class="mt-4">
            <img class="icon" src="/assets/icons/facebook.svg" />
          </b-col>
        </b-row>
      </b-col>
      <b-col md="12" class="mb-4 search" align-self="end">
        <img class="icon" src="/assets/icons/search.svg" />
      </b-col>
    </b-row>
    <div class="menu-options">
      <b-row>
        <b-col lg="12"><h1>HOME</h1></b-col>
        <b-col lg="12"><h1>PORTFOLIO</h1></b-col>
        <b-col lg="12"><h1>GALLERY</h1></b-col>
        <b-col lg="12"><h1>ABOUT US</h1></b-col>
        <b-col lg="12"><h1>CONTACT US</h1></b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Menu',
  data: () => ({
    toggled: false
  }),
  mounted() {
    this.$gsap.TweenMax.from('.menu-button', 2, {
      delay: 0.2,
      opacity: 0,
      ease: this.$gsap.Expo.easeInOut
    })
    this.$gsap.TweenMax.staggerFrom(
      '.social .col-md-12',
      2,
      {
        delay: 0.5,
        opacity: 0,
        ease: this.$gsap.Expo.easeInOut
      },
      0.2
    )
    this.$gsap.TweenMax.from('.search', 2, {
      delay: 1,
      opacity: 0,
      ease: this.$gsap.Expo.easeInOut
    })
  },
  methods: {
    toggle() {
      if (!this.toggled) {
        this.$gsap.TweenMax.fromTo(
          '.menu-wrapper',
          2,
          { width: 0 },
          {
            width: '100vw',
            ease: this.$gsap.Expo.easeInOut
          }
        )
        this.$gsap.TweenMax.staggerFromTo(
          '.menu-options .row .col-lg-12',
          2,
          {
            opacity: 0,
            y: 20,
            ease: this.$gsap.Expo.easeInOut
          },
          {
            opacity: 1,
            y: 0,
            ease: this.$gsap.Expo.easeInOut
          },
          0.2
        )
      } else {
        this.$gsap.TweenMax.staggerFromTo(
          '.menu-options .row .col-lg-12',
          2,
          {
            opacity: 1,
            y: 0,
            ease: this.$gsap.Expo.easeInOut
          },
          {
            opacity: 0,
            y: 20,
            ease: this.$gsap.Expo.easeInOut
          },
          0.2
        )
        this.$gsap.TweenMax.to('.menu-wrapper', 2, {
          width: 70,
          delay: 1.3,
          ease: this.$gsap.Expo.easeInOut
        })
      }
      this.toggled = !this.toggled
    }
  }
}
</script>

<style></style>
