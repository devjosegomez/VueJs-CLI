<template>
  <div id="app">
    <Navbar />
    <h1>{{name}}, {{ msg }}</h1>
    <AllFriends :friends="friends"/>
    <FriendsOnline :friends="friends"/>
    
  </div>
</template>

<script>
import Navbar from "./Navbar"
import AllFriends from "./AllFriends"
import FriendsOnline from "./FriendsOnline"

export default {
  components: {
    Navbar: Navbar,
    AllFriends: AllFriends,
    FriendsOnline: FriendsOnline
  },
  name: 'app',
  data () {
    return {
      msg: `Welcome to Your Vue.js App`,
      name: 'José',
      friends : [
                {name: "Paty", online: true},
                {name: "Uriel", online: false},
                {name: "Edgar", online: true},
                {name: "York", online: false}
            ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
