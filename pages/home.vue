<template>
  <div>

    <NavBar/>
    <BannerCarousel/>

    <h1 class="text-primary text-xl my-4 mx-4">
      Start Ordering
    </h1>

    <div class="flex justify-around grid grid-cols-2 gap-4 mx-4 my-4">
      <nuxt-link :to="'/products/' + 1">
        <FoodCard/>
      </nuxt-link>
      <FoodCard/>
      <FoodCard/>
      <FoodCard/>
      <FoodCard/>
      <FoodCard/>
      <FoodCard/>
      <FoodCard/>
      <FoodCard/>
      <FoodCard/>
    </div>

    <BottomNav/>

  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  transition: {
    name: 'home',
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
</style>


