<template>
    <div id="app" class="container">
      <h4>{{title}}</h4>
       <font-awesome-icon icon="fa-solid fa-user-secret" />Add Appointment
         <font-awesome-icon icon="fa-solid fa-user-secret" />
        <div v-for="(item, i) in appointments" v-bind:key="i">
          <h4>{{item.petName}}</h4>
          <p>{{item.aptNotes}}</p>
        </div>
    </div>
</template>

<script>
  import axios from "axios"
  export default {
    name: "MainApp",
    data: function() {
      return {
        title: "Appointment List",
        appointments: []
      };
    },
    mounted () {
      axios.get(".,public/data/appointments.json")
      .then(response => (this.appointments = response.data));
    }
  };
</script>