<script>
import HeaderApp from './components/HeaderApp.vue';
import FooterApp from './components/FooterApp.vue';
import MainApp from './components/MainApp.vue';
export default {
  components: {
    HeaderApp,
    FooterApp,
    MainApp,
  }
}
</script>

<template>
  <HeaderApp />
  <MainApp />
  <FooterApp />
</template>

<style lang="scss">
@use "./style/myStyle" as *;
</style>
