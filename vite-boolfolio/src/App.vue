<script >
import MainHeader from './components/MainHeader.vue';
import AppMain from './components/AppMain.vue';
import MainFooter from './components/MainFooter.vue';

export default {
  name:"",
  components:{
    MainHeader
  }
}
</script>

<template>

  <body>
    <header>
      <MainHeader/>
    </header>
  
    <main>
      <RouterView>

      </RouterView>
    </main>
  </body>
</template>

<style lang="scss">
@use "./styles/partials/general.scss";
</style>
