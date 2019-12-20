<template>
  <div v-editable="blok" class="page">
    <!-- eslint-disable-next-line vue/require-component-is -->
    <component :key="blok._uid" v-for="blok in blok.body" :blok="blok" :is="blok.component" ></component>
  </div>
</template>

<script>
export default {
  props: ['blok']
}
</script>
