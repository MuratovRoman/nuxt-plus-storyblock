<template>
  <div v-editable="blok" class="util__flex">
    <!-- eslint-disable-next-line vue/require-component-is -->
    <component :key="blok._uid" v-for="blok in blok.columns" :blok="blok" :is="blok.component" />
  </div>
</template>

<script>
export default {
  props: ['blok']
}
</script>
