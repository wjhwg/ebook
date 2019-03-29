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
}
document.addEventListener('DOMContentLoaded',() => {
  const html = document.querySelector('html')
  let fontsize = window.innerWidth / 10
  fontsize = fontsize > 50 ? 50 : fontsize
  html.style.fontSize = fontsize + 'px'
})
</script>
<style>
#app{
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>
