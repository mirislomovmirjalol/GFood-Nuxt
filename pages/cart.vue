<template>
  <div>
    <BackNav title="Cart" />

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
