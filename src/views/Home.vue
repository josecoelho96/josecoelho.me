<template>
  <v-content>
    <v-container id="top" text-xs-center>
      <h1 class="display-1">Hello! Welcome!</h1>
      <p>Welcome to my personal webpage</p>
      <div>
        <v-btn round :to="{ name: 'about' }" color="primary" dark>
          Read more about me
        </v-btn>
      </div>
      <div>
        <v-btn round :to="{ name: 'contact' }" color="primary" dark>
          My contacts
        </v-btn>
      </div>
    </v-container>
  </v-content>
</template>

<script>
export default {
  name: "Home"
};
</script>
