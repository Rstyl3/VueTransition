<template>
  <div id="app">
    <transition name="slide" mode="out-in" >
      <component @click="hndlClick" :is="currentTab"></component>
    </transition>
  </div>
</template>

<script>
import First from './components/First.vue'
import Second from './components/Second.vue'
import Third from './components/Third.vue'


export default {
  name: 'app',
  components: {
    First,
    Second,
    Third
  },
  data(){
    return{
      currentTab: First 
    }
  },
  methods:{ 
      hndlClick(v){
      this.currentTab = v
      }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  border: none;
  padding: 10px 25px;
  background-color: darkorchid;
  color: white;
  font-size: 15px;
}
.slide-enter-active {
  transition: all 1s;
}
.slide-leave-active {
  transition: opacity 0.3s ease-out;
}
.slide-enter {
  opacity: 0;
  transform: translateY(100px);
}
.slide-leave-to {
  opacity: 0;
}
</style>
