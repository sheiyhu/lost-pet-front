<template>
<div class="columns is-multiline">
  <div class="column is-half" v-for="pet in pets" :key="pet._id">
            <div class="card">
              <header class="card-header">
                <p class="card-header-title is-centered">{{ pet.name }}</p>
              </header>
              <div class="card-content">
                <figure class="image is-3by2">
                  <img :src="`${pet.imageUrl}`" />
                </figure>
              </div>
              <footer class="card-footer">
                <nuxt-link :to="`/pet/${pet._id}`" class="card-footer-item">
                  <button class="button is-dark">More about {{ pet.name }}</button>
                </nuxt-link>
              </footer>
            </div>
          </div>   </div>
</template>

<script>
export default {
    props: ['pets']
}
</script>

