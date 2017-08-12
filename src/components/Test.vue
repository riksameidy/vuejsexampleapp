<template>

<div class="test">
  <h1>{{title}}</h1>
  <input type="text" v-model="title">
  <p v-if="showname">{{user.first_name}}</p>
  <p v-else="showname">Nobody</p>
  <!-- <p v-text="user.first_name"></p> -->
  <ul>
    <li v-for="item in items">
      {{item.title}}
    </li>
  </ul>

  <button v-on:click="greet('Hello World')">Click</button>
  <br>
  <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit" name="" value="">
  <hr>
  <label for="">First Name</label><input type="text" v-model="user.first_name" name="" value="">
  <br>
  <label for="">Last Name</label><input type="text" v-model="user.last_name" name="" value="">
  <h3>{{fullname}}</h3>
  <h3>{{msg}}</h3>

</div>

</template>

<script>

  export default {
    name: 'test',
    props: {
      msg:{
        type:String,
        default:'foobar'
      }
    },
    data(){
      return{
      title:'Hello World' ,
      user: {
        first_name: 'Riksa',
        last_name: 'Meidy'
      },
      showname:true,
      items: [
        {title: 'item one'},
        {title: 'item two'},
        {title: 'item three'}
      ]
    };
  },
  methods: {
    greet : function(greeting){
      alert(greeting);
    },
    pressKey: function(e){
      console.log(e.target.value);
    },
    enterHit: function(){
      console.log('You Hit Enter');
    }
  },
  computed:{
    fullname: function(){
      return this.user.first_name + ' ' + this.user.last_name;
    }
  }

  }

</script>


<style scoped>

</style>
