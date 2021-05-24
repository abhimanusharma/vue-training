<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <!-- <Class3 v-bind:name="num" /> -->
    <!-- {{ num }} -->
    <!-- {{ sayHello("Rahul") }} -->
    <div v-if="num == 4">Hello</div>
    <div v-else-if="num == 55">Paras</div>
    <div v-else>Prince</div>

    <div v-for="item in arr" v-bind:key="item.id">
      {{ item.id }} {{ item.name }}
    </div>

    <button v-on:click="clicked">Click here</button>
    <button @click="clicked">Click here</button>

    <h1>{{ newData }}</h1>

    <input type="text" v-model="newData">

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// import Class3 from './components/Class3.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    //Class3
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
    }
  },
  created() {
    //this.sayHello("created hello");
    this.num = 55;
    //this.sayHello(this.num);
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
