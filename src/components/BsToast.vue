<template>
  <div class="hello">

    <div aria-live="polite" aria-atomic="true" class="position-relative">
      <!-- Position it: -->
      <!-- - `.toast-container` for spacing between toasts -->
      <!-- - `.position-absolute`, `top-0` & `end-0` to position the toasts in the upper right corner -->
      <!-- - `.p-3` to prevent the toasts from sticking to the edge of the container  -->
      <div class="toast-container position-absolute top-0 end-0 p-3">
        <!-- Then put toasts within -->
        <div
          class="toast"
          role="alert"
          aria-live="assertive"
          aria-atomic="true"
        >
          <div class="toast-header">
            <img src="" class="rounded me-2" alt="" />
            <strong class="me-auto">Bootstrap</strong>
            <small class="text-muted">just now</small>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="toast"
              aria-label="Close"
            ></button>
          </div>
          <div class="toast-body">See? Just like this.</div>
        </div>

        <!-- <div
          class="toast"
          role="alert"
          aria-live="assertive"
          aria-atomic="true"
        >
          <div class="toast-header">
            <img src="" class="rounded me-2" alt="" />
            <strong class="me-auto">Bootstrap</strong>
            <small class="text-muted">2 seconds ago</small>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="toast"
              aria-label="Close"
            ></button>
          </div>
          <div class="toast-body">
            Heads up, toasts will stack automatically
          </div>
        </div> -->
      </div>
    </div>

  </div>
</template>

<script>
import {
  Toast,
} from "bootstrap/dist/js/bootstrap.bundle.min.js";

// import { Popover } from "bootstrap/dist/js/bootstrap.bundle.min.js";

export default {
  name: "BsToast",
  props: {
    msg: String,
  },
  // components: {
  //   Tooltip,
  // },
  mounted() {
   

    var toastElList = [].slice.call(document.querySelectorAll(".toast"));
    var toastList = toastElList.map(function (toastEl) {
      new Toast(toastEl);
      
      // this.toasts.toast.add(t);
    });
    console.log(toastList);

    // this.$toast("tttt");
  },

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
