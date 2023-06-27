<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div class="buttons">
    <button @click="showModalOne">Pop-Up One</button>
    <button @click="showModalTwo">Pop-Up Two</button>
  </div>
  <div id="modal-1" class="modal" :style="{ display: modalOneShow }">
    <PopupOne @closemodalone="closeModalOne" />
  </div>
  <div id="modal-2" class="modal" :style="{ display: modalTwoShow }">
    <PopupTwo @closemodaltwo="closeModalTwo" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import PopupOne from './components/PopupOne.vue';
import PopupTwo from './components/PopupTwo.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld
    PopupOne,
    PopupTwo
  },
  data() {
    return {
      modalOneShow: "none",
      modalTwoShow: "none",
    }
  },
  methods: {
    showModalOne() {
      this.modalOneShow = "block";
    },
    closeModalOne() {
      this.modalOneShow = "none";
    },
    showModalTwo() {
      this.modalTwoShow = "block";
    },
    closeModalTwo() {
      this.modalTwoShow = "none";
    }
  }
}
</script>

<style>
@import url("../public/normalize.css");
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Caprasimo&display=swap');

#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */

}

* {
  color: #4A4447;
}

.popup {
  margin: 5% auto; /* 15% from the top and centered */
  padding: 10px;
  border: 5px solid #8B40F8;
  max-width: 500px; /* Could be more or less, depending on screen size */
  background-color: #EAD9FA;
}

.popup h1 {
  font-family: 'Caprasimo', cursive;
  letter-spacing: 3px;
  color: #8B40F8;
}

.popup h2 {
  font-family: 'Bebas Neue', sans-serif;
  letter-spacing: 3px;
}

h1, h3, .video {
  text-align: center;
}

.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

.buttons {
  margin: 20px;
}

.buttons button {
  margin: 5px;
}
</style>
