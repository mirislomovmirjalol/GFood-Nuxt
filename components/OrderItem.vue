<template>
  <div class="flex justify-between my-1">
    <div class="grid content-between my-4">
      <h3 v-if="this.product.title.length<22" class="font-medium text-lg">
        {{ this.product.title }}
      </h3>
      <h3 v-else class="font-medium text-lg">
        {{ this.product.title.substring(0, 18) + " ..." }}
      </h3>

      <p class="font-light text-md">{{ this.count }}</p>
    </div>
    <div class="flex items-center ml-2">
      <div class="flex justify-between items-center my-4">
        <span class="mx-2">${{ this.product.price }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "OrderItem",
  data: () => ({
    product: {
      title: 'Big Burger With Cheese',
      desc: 'Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things ',
      price: 48,
      quantity: 1
    },
    count: 1,
  }),
}
</script>

<style scoped>

</style>
