<!-- components/SignUp.vue -->
<template>
<header>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
</header>
  <div>
    <h1>Sign Up</h1>
    <form @submit.prevent="signUp">
      <div class="mb-3">
        <label for="name" class="form-label">Name</label>
        <input type="text" class="form-control" v-model="name" required>
      </div>
      <div class="mb-3">
        <label for="email" class="form-label">Email</label>
        <input type="email" class="form-control" v-model="email" required>
      </div>
      <div class="mb-3">
        <label for="employeeId" class="form-label">Employee ID</label>
        <input type="text" class="form-control" v-model="employeeId" required>
      </div>
      <div class="mb-3">
        <label for="phone" class="form-label">Phone</label>
        <input type="tel" class="form-control" v-model="phone" required>
      </div>
      <div class="mb-3">
        <label for="password" class="form-label">Password</label>
        <input type="password" class="form-control" v-model="password" required>
      </div>
      <div class="mb-3">
        <label for="confirmPassword" class="form-label">Confirm Password</label>
        <input type="password" class="form-control" v-model="confirmPassword" required>
      </div>
      <button type="submit" class="btn btn-primary">Create Account</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      employeeId: '',
      phone: '',
      password: '',
      confirmPassword: '',
    };
  },
  methods: {
    signUp() {
      this.$emit('sign-up', {
        name: this.name,
        email: this.email,
        employeeId: this.employeeId,
        phone: this.phone,
        password: this.password,
        confirmPassword: this.confirmPassword,
      });
    },
  },
};
</script>

<style scoped>
/* Add your styling here */
</style>
