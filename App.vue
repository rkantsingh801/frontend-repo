<template>
    <div>
      <h1>Users</h1>
      <ul>
        <li v-for="user in users" :key="user.id">
          {{ user.FirstName }} {{ user.LastName }} ({{ user.Email }})
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        users: [],
      };
    },
    mounted() {
      axios.get('http://localhost:3000/users').then((response) => {
        this.users = response.data;
      });
    },
  };
  </script>