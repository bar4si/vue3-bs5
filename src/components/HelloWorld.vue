<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <button
      type="button"
      class="btn btn-lg btn-danger"
      data-bs-toggle="popover"
      data-bs-trigger="hover focus"
      data-bs-html="true"
      title="Popover title"
      data-bs-content="And here's some amazing content. It's very engaging. Right?"
    >
      Click to toggle popover
    </button>

    <button
      type="button"
      class="btn btn-lg btn-danger"
      data-bs-toggle="popover"
      data-bs-trigger="hover focus"
      data-bs-html="true"
      title="2Popover title"
      data-bs-content="2And here's some <br>amazing content. It's very engaging. Right?"
    >
      Click to toggle popover
    </button>

    <button
      type="button"
      class="btn btn-secondary"
      data-bs-toggle="tooltip"
      data-bs-html="true"
      title="<em>Tooltip</em> <u>with</u> <b>HTML</b>"
    >
      Tooltip with HTML
    </button>

    <button
      type="button"
      class="btn btn-secondary"
      data-bs-toggle="tooltip"
      data-bs-html="true"
      title="2<em>Tooltip</em> <u>with</u> <b>HTML</b>"
    >
      Tooltip with HTML
    </button>

    <button
      type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      Launch demo modal
    </button>

    <!-- Modal -->
    <div
      class="modal fade"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
      data-bs-backdrop="static"
    >
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div>
          <div class="modal-body">...</div>
          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Tooltip,Popover,Toast } from "bootstrap/dist/js/bootstrap.bundle.min.js";

// import { Popover } from "bootstrap/dist/js/bootstrap.bundle.min.js";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  // components: {
  //   Tooltip,
  // },
  mounted() {
    var tooltipTriggerList = [].slice.call(
      document.querySelectorAll('[data-bs-toggle="tooltip"]')
    );
    var tooltipList = tooltipTriggerList.map(function (tooltipTriggerEl) {
      new Tooltip(tooltipTriggerEl);
    });
    console.log(tooltipList);

    var popoverTriggerList = [].slice.call(
      document.querySelectorAll('[data-bs-toggle="popover"]')
    );
    var popoverList = popoverTriggerList.map(function (popoverTriggerEl) {
      new Popover(popoverTriggerEl);
    });
    console.log(popoverList);

    var toastElList = [].slice.call(document.querySelectorAll(".toast"));
    var toastList = toastElList.map(function (toastEl) {
      new Toast(toastEl);
    });
     console.log(toastList);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
