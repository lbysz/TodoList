<template id="app">
  <div :style="bgImg">
    <main-header></main-header>
    <main-to-do></main-to-do>
    <main-footer></main-footer>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue'
import MainToDo from './components/MainToDo/MainToDo.vue'
import MainFooter from './components/MainFooter.vue'

export default {
  name: 'App',
  components:{
    MainHeader:MainHeader,
    MainToDo:MainToDo,
    MainFooter:MainFooter
  },
  data() {
    return {
      bgImg: {
        backgroundImage: "url(" + require("../src/assets/bg.jpg") + ")",
        backgroundRepeat: "no-repeat",
        height: "1000px",
        width: "100%",
        backgroundSize: "cover"
        }
     }
 },
}

</script>

<style scoped>
</style>
