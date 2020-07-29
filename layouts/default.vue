<!-- ./layouts/default.vue -->

<template>
  <div>
    <!-- begin navigation -->
    <nav class="navbar has-shadow" role="navigation" aria-label="main navigation">
      <div class="container">
        <div class="navbar-start has-text-centered">
          <nuxt-link active-class="is-active" to="/" class="navbar-item is-tab" exact>Home</nuxt-link>
          <nuxt-link
            active-class="is-active"
            to="/pet/new"
            class="navbar-item is-tab"
            exact
          >Post a lost pet</nuxt-link>
          <nuxt-link
            active-class="is-active"
            to="/pet/cats"
            class="navbar-item is-tab"
            exact
          >Lost cats</nuxt-link>
          <nuxt-link
            active-class="is-active"
            to="/pet/dogs"
            class="navbar-item is-tab"
            exact
          >Lost dogs</nuxt-link>
          <nuxt-link
            active-class="is-active"
            to="/pet/others"
            class="navbar-item is-tab"
            exact
          >Other animals</nuxt-link>
        </div>
      </div>
    </nav>
    <!-- end navigation -->

    <!-- displays the page component -->
    <nuxt />

    <!-- begin footer -->
    <!-- <footer class="footer has-background-black">
      <div class="content has-text-centered">
        <p class="has-text-white">
          <strong class="has-text-white">Pet adoption website</strong> by
          <a href="https://github.com/Jordanirabor">Jordan</a>
        </p>
      </div>
    </footer> -->
    <!-- end footer -->
  </div>
</template>

<style>
.main-content {
  margin: 20px 0;
}
body {
  font-family: "Open Sans Condensed", sans-serif;
}

p {
  font-size: 22px;
}

</style>