<template>
  <v-content>
    <v-container id="top" text-xs-center>
      <h1 class="display-1 mb-5">Contact me...</h1>
      <v-layout row wrap>
        <v-flex xs12 sm6 text-xs-center text-sm-right>
          <v-avatar size="140">
            <v-img
              class="elevation-6 mr-3"
              src="/img/photo.jpg"
              aspect-ratio="1"
            ></v-img>
          </v-avatar>
        </v-flex>
        <v-flex xs12 sm6 text-xs-center text-sm-left>
          <div>
            <div class="mt-2">
              <v-icon class="mr-2">person</v-icon>José Coelho
            </div>
            <div class="mt-2">
              <v-icon class="mr-2">cake</v-icon>April 3rd, 1996
            </div>
            <div class="mt-2">
              <v-icon class="mr-2">email</v-icon>me@josecoelho.me
            </div>
            <div class="mt-2">
              <v-icon class="mr-2">location_on</v-icon>Lisbon, Portugal
            </div>
          </div>
        </v-flex>
      </v-layout>
    </v-container>
  </v-content>
</template>
