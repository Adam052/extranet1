<template>
    <div class="list">
      <h3>Lista zgłoszeń</h3>
      <ul v-if="tickets.length">
        <li v-for="ticket in tickets" :key="ticket.id">
          <h4>{{ ticket.title }}</h4>
          <p>{{ ticket.description }}</p>
          <button @click="removeTicket(ticket.id)">Usuń</button>
        </li>
      </ul>
      <p v-else>Brak zgłoszeń do wyświetlenia.</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      tickets: Array
    },
    methods: {
  removeTicket(ticketId) {
    this.$emit('onRemoveTicket', ticketId);
  }
}
  }
  </script>
  
  <style>
  h3 {
    color: #333;
    text-align: center;
    margin-bottom: 20px;
  }
  
  ul {
    list-style: none;
    padding: 0;
  }
  
  li {
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    margin-bottom: 10px;
    padding: 15px;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: background-color 0.3s;
    word-wrap: break-word;
  }
  
  li:hover {
    background-color: #f0f0f0;
  }
  
  h4 {
    color: #007bff;
    margin: 0 0 10px 0;
  }
  
  p {
    margin: 0 0 10px 0;
    color: #555;
    overflow-wrap: break-word;
  }
  
  button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 8px 15px;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  button:hover {
    background-color: #007bff;
  }
  .list{
    margin-top: 20px;
  }
  
  @media (max-width: 600px) {
    li {
      padding: 10px;
    }
  
    h4 {
      font-size: 1.1em;
    }
  
    button {
      padding: 6px 10px;
      font-size: 0.9em;
    }
  }
  </style>
  