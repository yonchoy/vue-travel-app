<template>
  <div id="app">
    <TheNavigation />
    <transition name="fade" mode="out-in">
    <!-- here we should put key so the router-view is notified after the id is changed-->
    <router-view :key="$route.path"/>
    </transition>
  </div>
</template>
<script>
import TheNavigation from "@/components/TheNavigation.vue";

export default {
  components: {
    TheNavigation
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.slide-enter-active,
.slide-leave-active{
  transition: opacity 1s, transform 1s;
}

.slude-enter,
.slide-leave-to {
  opacity: 0;
  transform: translateX(-30%);
}



.moveUp-enter-active{
  animation: fadeIn 1s ease-in;
}

@keyframes fadeIn{
  0%{ opacity: 0;}
  50%{ opacity: 0.5;}
  100%{ opacity: 1;}
}
.moveUp-leave-active{
  animation: moveUp 0.3s ease-in;
}
@keyframes moveUp{
  0%{ transform: translateY(0)}
  100%{ transform: translateY(-200px)}
}

.fade-enter-active,
.fade-leave-active{
  transition: opacity 0.2s;
}

.fade-enter,.fade-leave-to{
  opacity: 0;
}

</style>
