<template>
    <form @submit.prevent="submit" class="login-form">
      <div class="form-group">
        <input v-model="credentials.username" type="text" placeholder="Login">
      </div>
      <div class="form-group">
        <input v-model="credentials.password" type="password" placeholder="Password">
      </div>
      <div class="form-group">
        <button type="submit">Login</button>
      </div>
    </form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        credentials: {
          username: '',
          password: ''
        }
      };
    },
    methods: {
      submit() {
        this.$emit('onLogin', this.credentials);
      }
    }
  }
  </script>
  
  <style>
  .login-form .form-group {
    margin-bottom: 15px; 
  }
  
  .login-form input[type="text"],
  .login-form input[type="password"] {
    width: 90%; 
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 10px;
  }
  
  .login-form button {
    width: 100%; 
    padding: 10px;
    border-radius: 4px;
    border: none;
    background-color: #007bff; 
    color: white; 
    cursor: pointer; 
  }
  
  .login-form button:hover {
    background-color: #0056b3;
  }
  </style>
  