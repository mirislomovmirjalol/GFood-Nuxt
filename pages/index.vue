<template>
  <div>

    <NavBar/>
    <transition name="fade" mode="out-in">
      <BannerSkeleton v-if="loading"/>

      <BannerCarousel v-else/>
    </transition>

    <h1 class="text-primary text-xl my-4 mx-4">
      Start Ordering
    </h1>

    <transition name="fade" mode="out-in">
      <CardSkeleton v-if="loading"/>

      <div v-else class="flex justify-around grid grid-cols-2 gap-4 mx-4 my-4 lg:grid-cols-4 mb-24">
        <nuxt-link v-for="product in products" :key="product.id" :to="'/products/' + product.id">
          <FoodCard :product="product" />
        </nuxt-link>
      </div>
    </transition>

    <BottomNav/>

  </div>
</template>

<script>
import {state} from './../store/index.js'

export default {
  name: 'IndexPage',
  transition: {
    name: 'home',
  },
  data: () => ({
    loading: true,
  }),
  mounted() {
    this.stopLoadind()
  },
  methods: {
    //after 2 seconds loading will stop
    stopLoadind() {
      setTimeout(() => this.loading = false, 2000);
    }
  },
  computed: {
    products() {
      return this.$store.state.products;
    }
  }
}
</script>

<style scoped>
.home-enter-to, .home-leave-active {
  transition: all .3s;
}

.home-enter, .home-leave-active {
  opacity: 0;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}

.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */
{
  opacity: 0;
}
</style>


