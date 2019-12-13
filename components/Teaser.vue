<template>
  <div v-editable="blok" class="teaser">
    <!-- eslint-disable-next-line vue/require-component-is -->
    <component v-if="slide" :blok="slide" :is="slide.component" />
    <div class="teaser__pag">
      <button
              @click="handleClick(index)"
              :key="index"
              v-for="(blok, index) in blok.body"
              :class="{'teaser__pag-dot--current': index == currentSlide}"
              class="teaser__pag-dot">Next</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['blok'],

  data () {
    return {
      currentSlide: 0
    }
  },

  computed: {
    slide () {
      const slides = this.blok.body.filter((slide, index) => {
        return this.currentSlide === index
      })
      if (slides.length) {
        return slides[0]
      }
      return null
    }
  },

  methods: {
    handleClick (index) {
      this.currentSlide = index
    }
  }
}
</script>

<style lang="sass" scoped>
.teaser
  &__pag
    width: 100%
    text-align: center
    margin: 30px 0
    &-dot
      text-indent: -9999px
      border: 0
      border-radius: 50%
      width: 17px
      height: 17px
      padding: 0
      margin: 5px 6px
      background-color: #ccc
      -webkit-appearance: none
      cursor: pointer
      outline: none
      &--current
        background-color: #000
</style>
