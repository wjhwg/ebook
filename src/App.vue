<template>
  <div id="app">
    <div class="font">
      hello world
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$store.dispatch('setTest', 101).then(() => {
      console.log(this.$store.state.book.test)
    })
  },
}
document.addEventListener('DOMContentLoaded',() => {
  const html = document.querySelector('html')
  let fontsize = window.innerWidth / 10
  fontsize = fontsize > 50 ? 50 : fontsize
  html.style.fontSize = fontsize + 'px'
})
</script>
<style>
.font{
  font-family: 'Days One';
  font-size: 1rem;
  color: aqua;

}
</style>
