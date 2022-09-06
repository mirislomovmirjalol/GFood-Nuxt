<template>
  <div class="flex flex-col h-screen">
    <BackNav title="Product"/>

    <main class="flex-grow">
      <product-photo-carousel/>
      <h2 v-if="this.product.title.length<36" class="m-4 text-xl font-semibold">
        {{ this.product.title }}
      </h2>
      <h2 v-else class="m-4 text-xl font-semibold">
        {{ this.product.title.substring(0, 35) + " ..." }}
      </h2>
      <div class="mx-4 text-md text-primary">Description</div>
      <p class="m-4 text-sm">{{ this.product.desc }}</p>
    </main>

    <footer class="mx-4 pb-4 border-t border-t-primary sticky top-[100vh]">
      <div class="flex justify-between items-center my-4">
        <p>${{ this.product.price }}</p>
        <div>
          <button @click="this.reduce" class="btn btn-outline dark:btn-circle">
            -
          </button>
          <span class="mx-2">{{ this.count }}</span>
          <button @click="count++" class="btn btn-outline dark:btn-circle">
            +
          </button>
        </div>
      </div>
      <button class="btn btn-primary btn-block">
        Add To Basket
      </button>
    </footer>

  </div>
</template>

<script>
export default {
  name: "product",
  data: () => ({
    product: {
      title: 'Big Burger With Cheese',
      desc: 'Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things Very Nice Burger With A Lot Of Stuped Things ',
      price: 48
    },
    count: 0,
  }),
  methods: {
    reduce() {
      if (this.count > 0) {
        this.count--
      }
    },
  },
}
</script>

<style scoped>
.home-enter-to, .home-leave-to {
  transition: all .3s;
}

.home-enter, .home-leave-to {
  transform: translateX(100%);
}
</style>
