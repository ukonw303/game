<template>
  <div id="app">
    <HelloWorld msg=".."/>  
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
export default {
  name: "App",
  components: {
    HelloWorld,
  },

  data: function () {
    return {
  
    };
  },

  methods: {
    
  },
};
</script>

<style>

body{
  background-image: url(https://i.pinimg.com/originals/c8/66/51/c86651af900838110f485878671947dc.gif);
  background-size: 100%;
}
#app {
font-family: 'Metal Mania', cursive;  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 30px;
}

.cardtop{
  font-family: 'Bungee', cursive;
  font-size: 40px;
}
/*body{
  background-image: url(./assets/b1.gif);
  background-attachment:fixed;
}*/
</style>


