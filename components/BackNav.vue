<template>
  <div class="navbar bg-base-100">
    <div class="navbar-start">
      <button @click="goToPrev()" class="btn btn-square btn-ghost">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
             class="w-6 h-6">
          <path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18"/>
        </svg>
      </button>
    </div>
    <div class="navbar-center">
      <button class="btn btn-ghost normal-case text-xl">{{ title }}</button>
    </div>
    <div class="navbar-end">
      <button class="btn btn-square btn-ghost">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="inline-block w-5 h-5 stroke-current"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z"></path></svg>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "BackNav",
  methods: {
    goToPrev() {
      this.$router.go(-1);
    },
  },
  props: ['title']
}
</script>

<style scoped>

</style>
