<template>
 <div class="container">
  <Passmessage @submit="onSubmit" msg="Pass message"/>
  <div class="textes">{{ outputFrom }}</div>
 </div>
</template>

<script>
import Passmessage from './components/Passmessage.vue'

export default {
  name: 'App',
  components: {
    Passmessage
  },

  data(){
    return{
      outputFrom:'',
    }
  },

  methods:{
    onSubmit(messageValue){
      this.outputFrom = messageValue
    }
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
