<template>
    <div class="helpdesk">
      <NewTicketForm @onNewTicket="addNewTicket" />
      <TicketList :tickets="tickets" @onRemoveTicket="removeTicket" />
    </div>
  </template>
  
  <script>
  import NewTicketForm from '~/components/NewTicketForm.vue';
  import TicketList from '~/components/TicketList.vue';
  
  export default {
    components: {
      NewTicketForm,
      TicketList
    },
    data() {
      return {
        tickets: [] 
      };
    },
    methods: {
      addNewTicket(newTicket) {
        
        const newId = Date.now(); 
  
        this.tickets.push({ id: newId, ...newTicket });
      },
      removeTicket(ticketId) {
        this.tickets = this.tickets.filter(ticket => ticket.id !== ticketId);
      }
    }
  }
  </script>

  <style>
    .helpdesk {
        max-width: 800px;
        margin: 20px auto;
        padding: 20px;
    }
</style>
  