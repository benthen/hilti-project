<!-- components/Home.vue -->
<template>
<header>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
</header>
  <div>
    <header>
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
          <a class="navbar-brand" href="#">Your Website</a>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
              <li v-for="menuItem in menuItems" :key="menuItem" class="nav-item">
                <router-link :to="`/${menuItem.toLowerCase()}`" class="nav-link">{{ menuItem }}</router-link>
              </li>
            </ul>
            <button @click="logout" class="btn btn-outline-danger">Logout</button>
          </div>
        </div>
      </nav>
    </header>
    <div class="container mt-3">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
export default {
  props: ['menuItems'],
  methods: {
    logout() {
      this.$emit('logout');
    },
  },
};
</script>

<style scoped>
/* Add your styling here */
</style>
