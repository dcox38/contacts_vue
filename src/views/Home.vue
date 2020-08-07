<template>
  <div class="home">
    <h1>{{ "It's a beautiful day in the neighborhood" }}</h1>
    <h1>{{ name }}</h1>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      name: "Danimal", 
      contacts: []
    };
  },
  created: function() {
    this.indexContacts();
  },
  methods: {
    indexContacts: function() {
      console.log('getting contacts...');
      axios.get("api/contacts").then(response => {
        this.contacts = response.data;
      });
    }
  }
};
</script>