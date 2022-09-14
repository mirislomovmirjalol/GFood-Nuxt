<template>
  <div class="flex flex-col h-screen">
    <BackNav title="Product"/>

    <main class="flex-grow">
      <product-photo-carousel :images="product.image"/>
      <h2 v-if="this.product.name.length<36" class="m-4 text-xl font-semibold">
        {{ this.product.name }}
      </h2>
      <h2 v-else class="m-4 text-xl font-semibold">
        {{ this.product.name.substring(0, 35) + " ..." }}
      </h2>
      <div class="mx-4 text-md text-primary">Description</div>
      <p class="m-4 text-sm">{{ this.product.desc }}</p>
    </main>

    <footer class="mx-4 pb-4 border-t border-t-primary sticky top-[100vh]">
      <div class="flex justify-between items-center my-4">
        <p>${{ this.count * this.product.price }}</p>
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
import {state} from "@/store/index.js";

export default {
  name: "product",
  data: () => ({
    count: 1,
  }),
  methods: {
    reduce() {
      if (this.count > 1) {
        this.count--
      }
    },
  },
  computed: {
    product() {
      return this.$store.state.products[this.$route.params.id];
    }
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
