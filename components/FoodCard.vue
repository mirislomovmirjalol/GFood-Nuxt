<template>
  <div>
    <div class="card shadow-lg dark:shadow-primary dark:shadow-md">
      <img
        class="border-b-2 border-b-primary"
        src="https://images.unsplash.com/photo-1616431575978-ad28681d658e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8c3VzaGl8ZW58MHwyfDB8fA%3D%3D&auto=format&fit=crop&w=800&q=60"
        alt="" srcset="">
      <div class="flex flex-col content-center px-2 py-2 card-title text-center">
        <h3 v-if="this.product.name.length<23" class="text-xs">
          {{ this.product.name }}
        </h3>
        <h3 v-else class="text-xs">
          {{ this.product.name.substring(0,20)+"..." }}
        </h3>
        <p class="text-sm font-medium">${{ this.product.price }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FoodCard",
  data:()=>({
    product: {
      name: 'Big Burger With Cheese',
      price: 48
    }
  })
}
</script>

<style scoped>

</style>
