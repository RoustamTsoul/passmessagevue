<template>
 <div class="container">
  <Passmessage msg="Pass message"/>
 </div>
</template>

<script>
import Passmessage from './components/Passmessage.vue'

export default {
  name: 'App',
  components: {
    Passmessage
  }
}
</script>

<style>
.container{
width: 95%;
height:100vh;
margin:auto;
display:flex;
justify-content:center;
align-items:center;
}
</style>
