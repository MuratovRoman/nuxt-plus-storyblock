<template>
  <div class="util__flex-eq" v-editable="blok">
    <h1>{{ blok.name }}</h1>
  </div>
</template>

<script>
export default {
  props: ['blok']
}
</script>
