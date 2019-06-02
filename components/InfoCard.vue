<template>
  <div class="info-card">
    <b-row class="mb-5">
      <b-col :id="`card_${index}`" md="12">
        <img :src="src" />
        <span class="year">2018</span>
      </b-col>
      <b-col md="12" class="mt-3 mb-1">
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
  mounted() {
    VanillaTilt.init(document.querySelector(`#card_${this.index}`))
  }
}
</script>

<style></style>
