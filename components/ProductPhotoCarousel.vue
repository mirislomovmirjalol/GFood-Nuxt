<template>
  <div class="w-full carousel">
    <div v-for="image in images" :key="image.id" class="carousel-item w-full">
      <img
        :src="image.src"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductPhotoCarousel",
  props: ['images']
}
</script>

<style scoped>

</style>
