<template>
<div class="top"><h1>BIURO OBSŁUGI STUDENTA</h1></div>
    <div class="login-container">
        
        <img src='~/assets/logo.png' />

      <LoginForm @onLogin="handleLogin" />
    </div>
  </template>
  
  <script>
  import LoginForm from '~/components/LoginForm.vue'
  
  export default {
    components: {
      LoginForm
    },
    methods: {
      handleLogin(credentials) {
        const defaultUsername = "admin";
        const defaultPassword = "admin";
  
        if (credentials.username === defaultUsername && credentials.password === defaultPassword) {
          localStorage.setItem('user-token', 'dummy-token');
          this.$router.push('/helpdesk');
        } else {
          alert("Nieprawidłowe dane logowania");
        }
      }
    }
  }
  </script>
  
  <style>
.top{
    background-color: #007bff;
    color: white;
    display: flex;
    text-align: center;
    justify-content: center;
    padding-top: 1%;
    height: 10vh;
}
.login-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center; 
  min-height: 80vh;
  padding: 20px;
  background-color: #f4f4f4;
  overflow: hidden; 
}

.login-container img {
  max-width: 200px;
  margin-bottom: 20px; 
}

@media (max-width: 600px) {
  .top {
    font-size: 14px; 
    padding-top: 10px;
    height: 15vh; 
  }

  .login-container {
    padding: 10px;
    min-height: 90vh; 
  }

  .login-container img {
    max-width: 150px; 
    margin-bottom: 15px;
  }
}

@media (min-width: 601px) and (max-width: 1024px) {
  .top {
    font-size: 16px;
    height: 9vh; 
  }

  .login-container {
    padding: 15px;
    min-height: 85vh; 
  }

  .login-container img {
    max-width: 180px; 
    margin-bottom: 18px;
  }
}
  </style>
  