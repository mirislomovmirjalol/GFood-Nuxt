<template>
  <div>
    <BackNav title="Cart"/>
    <div class="mx-4 my-4">
      <CartItem/><CartItem/><CartItem/><CartItem/>
    </div>
    <div class="flex justify-between mx-4">
      <h2 class="font-bold">Total</h2>
      <p class="">$122</p>
    </div>
    <div class="m-4">
    <button class="btn btn-block btn-primary">Checkout</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
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
