<template>
<div id="toast_id" class="toast" role="alert" aria-live="assertive" aria-atomic="true">
  <div class="toast-header">
    <img src="" class="rounded me-2" alt="">
    <strong class="me-auto">Bootstrap</strong>
    <small>11 mins ago</small>
    <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>
  </div>
  <div class="toast-body">
    Hello, world! This is a toast message.
  </div>
</div>

<button type="button" @click="test_toast()">Test toast</button>
  <BsToast :toasts="toasts" />
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld v-bind:toasts="toasts" msg="Welcome to Your Vue.js App" />
  
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import BsToast from "./components/BsToast.vue";


import {
  Toast,
} from "bootstrap/dist/js/bootstrap.bundle.min.js";

export default {
  name: "App",
  components: {
    HelloWorld,
    BsToast,
  },
  data() {
    return {
      toasts: [],
    };
  },
  methods: {
    test_toast(){
      console.log("test toast", this.toasts);
      this.toasts.push("test2");
       console.log("test toast", this.toasts);

       let myToastEl = document.getElementById('toast_id')
       let t = Toast.getOrCreateInstance(myToastEl);
       t.show();
    }
  },
};
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
