<!-- ./pages/index.vue -->

<template>
  <div>
    <header-component/>
    <!-- begin main content -->
    <section class="main-content">
      <div class="container">
        <h1 class="title has-text-centered">Available pets</h1>
        <div>
         <list-component :pets=pets />
        </div>
      </div>
    </section>
    <!-- end main content -->
  </div>
</template>

<script>
import listComponent from "~/components/listComponent";
import headerComponent from "~/components/headerComponent";
export default {
  head: {
    title: "Home"
  },
  components: {
    listComponent,headerComponent
  },
  async asyncData({$axios}) {
    try {
      let data = await $axios.$get("http://localhost:3000/api/pets")
      return {pets : data}
    } catch (e) {
      console.error("SOMETHING WENT WRONG :" + e);
    }
  },
  // data() {
  //   return {
  //     pets: []
  //   };
  // }
};
</script>
