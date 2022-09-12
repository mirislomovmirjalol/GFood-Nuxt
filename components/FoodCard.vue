<template>
  <div>
    <div class="card shadow-lg dark:shadow-primary dark:shadow-md">
      <img
        class="border-b-2 border-b-primary"
        :src="product.image[0].src"
        alt="" srcset="">
      <div class="flex flex-col content-center px-2 py-2 card-title text-center">
        <h3 v-if="product.name.length<23" class="text-xs">
          {{ product.name }}
        </h3>
        <h3 v-else class="text-xs">
          {{ product.name.substring(0,20)+"..." }}
        </h3>
        <p class="text-sm font-medium">${{ product.price }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FoodCard",
  props: ['product']
}
</script>

<style scoped>

</style>
