<template>
    <form @submit.prevent="submitTicket">
      <input v-model="newTicket.title" type="text" placeholder="Tytuł zgłoszenia">
      <textarea v-model="newTicket.description" placeholder="Opis"></textarea>
      <button type="submit">Dodaj zgłoszenie</button>
    </form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTicket: {
          title: '',
          description: ''
        }
      };
    },
    methods: {
      submitTicket() {
        this.$emit('onNewTicket', { ...this.newTicket });
        this.newTicket.title = '';
        this.newTicket.description = '';
      }
    }
  }
  </script>

<style>
form {
  max-width: 500px;
  margin: 0 auto;
  padding: 20px;
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

input[type="text"],
textarea {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

textarea {
  resize: vertical;
  min-height: 100px;
}

button {
  background-color: #28a745;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1em;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #218838;
}

@media (max-width: 768px) {
  form {
    padding: 15px;
  }

  input[type="text"],
  textarea {
    padding: 8px;
  }

  button {
    padding: 8px 16px;
  }
}
</style>
  