<template>
  <div>
    <NavBar/>

    <transition name="fade" mode="out-in">
      <BannerSkeleton v-if="loading"/>

      <div v-else class="card mx-4 mt-4 shadow-lg bg-base-content text-base-100 dark:shadow-primary">
        <ul class="steps py-8">
          <li class="step step-primary">Order confirming</li>
          <li class="step">Order processed</li>
          <li class="step">Order is on the way</li>
          <li class="step">Order completed</li>
        </ul>
      </div>
    </transition>

    <div class="mx-4 my-4 border-b border-b-primary">
      <OrderItem/>
      <OrderItem/>
      <OrderItem/>
      <OrderItem/>
    </div>

    <div class="flex justify-between mx-4 my-4">
      <h3 class="font-medium text-lg">Total</h3>
      <p class="font-light text-md">$120</p>
    </div>


    <BottomNav/>
  </div>
</template>

<script>
export default {
  name: "order",
  transition: {
    name: 'home',
  },
  data: () => ({
    loading: true,
  }),
  methods: {
    //after 2 seconds loading will stop
    stopLoadind() {
      setTimeout(() => this.loading = false, 2000);
    }
  },
  mounted() {
    this.stopLoadind()
  },
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
