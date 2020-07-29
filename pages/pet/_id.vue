<!-- ./pages/pet/_id/index.vue -->

<template>
  <div class="main-content">
    <div class="container">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title is-centered has-text-danger">{{ pet.name }}</p>
        </header>
        <div class="card-content has-background-dark">
          <figure class="image is-1by1">
            <img class :src="`${pet.imageUrl}`" />
          </figure>
        </div>
        <br />
        <h4 class="title is-5 is-marginless">
          <p class="has-text-centered has-text-success">About</p>
          <br />
          <p class="has-text-centered has-text-primary">
            <strong>{{ pet.description }}</strong>
          </p>
          <hr />
        </h4>
        <h4 class="title is-5 is-marginless has-text-success">
          <p class="has-text-centered">Found at</p>
          <br />
          <p class="has-text-centered has-text-primary">
            <strong>{{ pet.address }}</strong>
          </p>
          <hr />
        </h4>
        <h4 class="title is-5 is-marginless has-text-success">
          <p class="has-text-centered">Found on</p>
          <br />
          <p class="has-text-centered has-text-primary">
            <strong>{{ pet.date }}</strong>
          </p>
          <hr />
        </h4>
        <h4 class="title is-5 is-marginless has-text-success">
          <p class="has-text-centered">Contact</p>
          <br />
          <p class="has-text-centered has-text-primary">
            <strong>{{ pet.contact }}</strong>
          </p>
          <hr />
        </h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  validate({ params }) {
    return /^[a-f\d]{24}$/i.test(params.id);
  },
  async asyncData({ params, $axios }) {
    try {
      let pet = await $axios.$get(`http://localhost:3000/api/pet/${params.id}`)
      return { pet };
    } catch (e) {
      console.error("SOMETHING WENT WRONG :" + e);
      return { pet: {} };
    }
  },
  head() {
    return {
      title: this.pet.name,
      meta: [
        {
          hid: "description",
          name: "description",
          content: this.pet.description
        }
      ]
    };
  }
};
</script>