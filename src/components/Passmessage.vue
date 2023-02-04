<template>
  <div class="message-container">
    <h3 class="title">{{msg}}</h3>
    <p class="under-line"></p>
    <form class="inputField" @submit.prevent="sendMessage">
      <input class="input" id="message-input" type="text" placeholder="Write here..." required v-model="messageValue" >
      <button class="btn btn-send">Submit</button>
    </form>
    <!-- <p id="message-output" style="text-align:center" text-transform:uppercase; ></p>  -->
  </div>
</template>

<script>
export default {
  name: 'Passmessage',
  props: {
    msg: String
  },

  data(){
    return{
      messageValue:'',
    }
  },

  emits:['submit'],

  methods:{
    sendMessage(){
      console.log('messageValue', this.messageValue)
      this.$emit('submit', this.messageValue)
      this.messageValue = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.message-container{
display: flex;
justify-content: center;
flex-direction: column;
border: 1px solid rgb(23, 105, 82);
background: #2c895f;
border-radius:10px;
width: 500px;
height: auto;
margin: auto;
padding: 0 30px;
box-shadow: 12px 12px 2px 1px rgb(8, 97, 97);
}

.title {
text-align: center;
font-weight: bold;
color:white;
margin-top: 10px;
margin-bottom: 10px;
}

.under-line{
border-bottom: 2px solid rgb(8, 97, 97);
margin-top: 10px;
}

.inputField{
display: flex;
flex-direction: column;
justify-content: center;
padding: 10px 5px;
width:500px;
box-sizing: border-box;
color: rgba(0, 0, 0, 0.847);
font-size: 1rem;
font-weight: 200;
align-content: center;
}

.input{
  height: 40px;
  border-radius: 10px;
  border: none;
}

.btn{
padding: 10px;
cursor: pointer;
background: rgb(16, 98, 73);
max-width: 400px;
margin: 10px 45px;
color:white;
text-align: center;
border: none;
border-radius: 10px;
font-size:1rem;
text-transform: uppercase;
letter-spacing: 1px;
font-weight: bold;
}

.btn:hover{
background: rgba(0, 0, 0, 0.5);    
}

</style>
