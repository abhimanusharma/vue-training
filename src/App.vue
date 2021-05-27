<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Class3 v-bind:name="num" />

    <button @click="getDummyData">Get Posts</button>

    <div class="list">
      <ul class="list-ul">
        <li v-for="post in posts" :key="post.id">{{post.title}}</li>
      </ul>
    </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Class3 from './components/Class3.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Class3
  },
  data() {
    return {
      num: 4,
      arr: [{
        id: 1,
        name: "Paras"
      }, {
        id: 2,
        name: "Tamanna"
      }, {
        id: 3,
        name: "Prince"
      }],
      newData: "Data to update",
      posts: []
    }
  },
  created() {
    //this.sayHello("created hello");
    this.num = 55;
    //this.sayHello(this.num);
    var element = document.getElementById("app");
    // console.log(document);
    // console.log(window);
    console.log(element.id);
  },
  mounted() {
   // this.sayHello("mounted hello");
    this.num = 66;
    //  this.sayHello(this.num);
  },
  methods: {
    sayHello(greetings) {
      console.log(greetings);
      return greetings;
    },
    clicked() {
      this.newData = "Clicked";
    },
    async getDummyData() {
      axios.get(`https://jsonplaceholder.typicode.com/posts`)
      .then(response => {
        this.posts = response.data;
        //console.log(this.posts);
      })
      .catch((error) => {
        console.log(error.response.data);
      })
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
  margin-top: 60px;
}
</style>
