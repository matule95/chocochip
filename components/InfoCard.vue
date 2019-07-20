<template>
  <div
    :id="`info_card_${index}`"
    class="info-card"
    :class="{ 'not-selected': !selected, selected: selected }"
    @click="isSelected"
  >
    <b-row class="mb-5">
      <b-col :id="`card_${index}`" md="12">
        <img :src="src" />
        <span class="year">2018</span>
      </b-col>
      <b-col :id="`model_name_${index}`" md="12" class="mt-3 mb-1">
        <h6>Model name</h6>
      </b-col>
      <b-col md="12" class="text-justify">
        <p>
          Everything is happy if you choose to make it that way. See. We take
          the corner of the brush and let it play back-and-forth.
        </p>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import VanillaTilt from 'vanilla-tilt'
export default {
  name: 'InfoCard',
  props: {
    src: {
      required: true,
      type: String
    },
    index: {
      required: true,
      type: Number
    }
  },
  data: () => ({
    selected: false
  }),
  mounted() {
    VanillaTilt.init(document.querySelector(`#card_${this.index}`))
    // const tm = this.$gsap.TweenMax.fromTo(
    //   `#card_${this.index}`,
    //   2,
    //   { autoAlpha: 0, ease: this.$gsap.Expo.easeInOut },
    //   { autoAlpha: 1, ease: this.$gsap.Expo.easeInOut }
    // )
    // const scene = new this.$scrollmagic.Scene({
    //   triggerElement: `#info_card_${this.index}`,
    //   triggerHook: 1, // show, when scrolled 10% into view
    //   duration: '50%', // hide 10% before exiting view (80% + 10% from bottom)
    //   offset: 50 // move trigger to center of element
    // }).setTween(tm)
    // this.$ksvuescr.$emit('addScene', 'photographyScene', scene)
  },
  methods: {
    isSelected() {
      this.selected = true
      this.$emit('clicked', this.index)
    }
  }
}
</script>

<style></style>
