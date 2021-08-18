<template>
 <div>
   <Nav />
    <Ass/>
 </div>

</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Ass from "./components/Ass.vue"
import Nav from "./components/Nav.vue"
export default {
  name: 'App',
  components: {
    Ass,
    Nav
    
  }
}
</script>

<style>

</style>
