<template>
    <v-toolbar
      flat
      class="nav-bar"
    >
      <v-spacer></v-spacer>
      
      <!-- Navigation items, centered -->
      <v-btn text to="/" class="nav-item">Home</v-btn>
      <v-btn text to="/news" class="nav-item">News</v-btn>
      <v-btn text to="/colleges" class="nav-item">Colleges</v-btn>
      <v-btn text to="/players" class="nav-item">Players</v-btn>
      <v-btn text to="/rankings" class="nav-item">Rankings</v-btn>
      <v-btn text to="/schedule" class="nav-item">Schedule</v-btn>
      <v-btn text to="/camps" class="nav-item">Camps & Clinics</v-btn>
      
      <v-spacer></v-spacer>
      
      <!-- Sign In button, moved to the right -->
      <v-btn text to="/signin" class="nav-item sign-in">
      <v-img
        src="@/assets/sign-in.svg"
        alt="Sign In"
        width="16"
        height="16"
        class="icon"
      />
      Sign In
    </v-btn>
    </v-toolbar>
  </template>
  
  <script>
  export default {
    name: 'NavBar',
  };
  </script>
  
  <style scoped>
  /* Custom styling for the v-toolbar */
  .nav-bar {
    background-color: #003784;
    color: white;
  }
  
  /* Style for individual nav items */
  .nav-item {
    color: white;
    margin: 0 15px;
    font-size: 20px;
    font-family: "Roboto;";
  }
  
  /* Sign In button specific styling */
  .sign-in {
    margin-right: 0;
  }
  
  /* Add hover effect */
  .nav-item:hover {
    background-color: rgba(255, 255, 255, 0.1);
  }
  </style>
  