<template>
<header>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
</header>
<div>
    <h1>Login</h1>
    <form @submit.prevent="login">
      <div class="mb-3">
        <label for="employeeId" class="form-label">Employee ID</label>
        <input type="text" class="form-control" v-model="employeeId" required>
      </div>
      <div class="mb-3">
        <label for="password" class="form-label">Password</label>
        <input type="password" class="form-control" v-model="password" required>
      </div>
      <div class="mb-3 form-check">
        <input type="checkbox" class="form-check-input" id="keepSignIn" v-model="keepSignIn">
        <label class="form-check-label" for="keepSignIn">Keep me signed in</label>
      </div>
      <div class="mb-3">
        <a href="#">Forgot Password?</a>
      </div>
      <button type="submit" class="btn btn-primary">Login</button>
    <router-link to="/signup" class="btn btn-secondary">Sign Up</router-link>    
    </form>
  </div>
</template>

<script>

/*import SignUp from './SignUp.vue';*/
export default {
  data() {
    return {
      employeeId: '',
      password: '',
      keepSignIn: false,
    };
  },
  methods: {
    login() {
      this.$emit('login', {
        employeeId: this.employeeId,
        password: this.password,
        keepSignIn: this.keepSignIn,
      });
    },
  },
  
};
</script>

<style scoped>
/* Add your styling here */
</style>
