<template>
  <div class="filters">
    <b-col class="active">
      <span>EDITORIAL</span>
    </b-col>
    <b-col>
      <span>JOURNALISM</span>
    </b-col>
    <b-col>
      <span>WEDDINGS</span>
    </b-col>
    <b-col>
      <span>BDAY SESSION</span>
    </b-col>
    <b-col>
      <span>NEW BORN</span>
    </b-col>
  </div>
</template>

<script>
export default {
  name: 'Filters',
  mounted() {
    this.$gsap.TweenMax.staggerFrom(
      '.filters .col',
      2,
      {
        delay: 2,
        opacity: 0,
        ease: this.$gsap.Expo.easeInOut
      },
      0.2
    )
  }
}
</script>

<style></style>
