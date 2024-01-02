<template>
  <div class="checkDone"> 
  <div class="m-2 text-dark fs-4 fw-bold p-2 text-start ">

    <div class="d-flex justify-content-between align-items-center ">
      <div class="div">
        <div class="" style="cursor: pointer" v-on:click="open()">
          {{ item.title }}
          <div class="fs-5" v-if="showDetail">
            {{ item.detail }}
          </div>
        </div>
      </div>

      <!-- icons div  -->
      <div class=" " style="cursor: pointer">
        <span class="material-icons ms-1"> edit </span>
        <span class="material-icons ms-1"> delete_forever </span>
        <span class="material-icons ms-1"> check_circle </span>
      </div>
    </div>

  </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "SingleProject",

  props: ["item"],

  data() {
    return {
      showDetail: false,
    };
  },

  computed: {},

  watch: {},

  methods: {
    open() {
      this.showDetail = !this.showDetail;
    },
  },

  components: {},

  setup() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
span:hover {
  text-shadow: 3px 3px rgb(255, 255, 255);
}
.div:hover {
  text-shadow: 1px 1px rgb(255, 255, 255);
}
.checkDone{
  border-left: 7px solid red;
}
</style>
