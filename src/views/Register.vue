<template>
  <div>
    <h1>Register</h1>

    <input
    type="text"
    name="email"
    v-model="email"
    placeholder="Email" />
    <br>
    <input
    type="password"
    name="password"
    v-model="password"
    placeholder="Password" />
    <br>
    <button
      @click="register">
      Register
    </button>
  </div>
</template>

<script>
/* eslint-disable no-console */
import AuthenticationService from '@/services/AuthenticationService';

export default {
  name: 'Register',
  data() {
    return {
      email: '',
      password: '',
    };
  },
  methods: {
    async register() {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password,
      });
      console.log(response.data);
    },
  },
};
</script>
