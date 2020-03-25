<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <my-button class='my-2' />
    <my-button class='my-2' />

    <h2>Listado de planes de programación</h2>

<!--     <div class="planes">

      <plan v-for='(plan, i) in planes' :key = 'i' :titulo='plan.plan' />

    </div> -->

    <planes/>

  </div>
</template>

<script>
/* import HelloWorld from './components/HelloWorld.vue' */
import MyButton from './components/MyButton.vue'
import Planes from './components/Planes.vue'

export default {
  name: 'App',
  components: {
    MyButton,
    Planes
  },
  data(){
    return{
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}

</style>
