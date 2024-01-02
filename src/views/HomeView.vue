<template>
  <div class="home">
    <h1 class="text-danger fs-3 fw-bold text-decoration-underline">
      Project Planner 
    </h1>
      <!-- v-for="(task, index) in filterTask" :key="index" -->
      <div
        class="bg-primary my-3 p-3 shadow-lg "
        v-for="(item, index) in data"
        :key="index"
      >
        <!-- item sent parent to child with props :item then catch with props:[]-->
        <SingleProject :item="item"></SingleProject>
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import SingleProject from "../components/SingleProject.vue";

export default {
  name: "HomeView",
  components: { SingleProject },
  data() {
    return {
      data: "",
    };
  },
  mounted() {
    fetch("http://localhost:3000/projects")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        // console.log(data);
        this.data = data;
      })
      .catch((err) => console.log(err.message()));
  },
};
</script>
