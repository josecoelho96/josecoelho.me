<template>
  <nav>
    <v-toolbar app dark color="primary">
      <v-toolbar-side-icon @click="isDrawOpen = !isDrawOpen" />
      <router-link :to="{ name: 'home' }" class="white--text">
        <v-toolbar-title class="headline text-uppercase">
          <span class="font-weight-light">{{ name.firstName }}</span>
          <span class="font-weight-bold">{{ name.lastName }}</span>
        </v-toolbar-title>
      </router-link>
      <v-spacer />
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          v-for="option in menuOptions"
          :key="option.option"
          flat
          :to="{ name: option.routeName }"
          exact
        >
          {{ option.text }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer v-model="isDrawOpen" app temporary fixed>
      <v-list class="pa-1">
        <v-list-tile :to="{ name: 'home' }">
          <v-list-tile-content>
            <v-list-tile-title class="text-uppercase secondary--text">
              {{ name.firstName }} {{ name.lastName }}</v-list-tile-title
            >
          </v-list-tile-content>
        </v-list-tile>
      </v-list>

      <v-list class="pt-0" dense>
        <v-divider />
        <v-list-tile
          v-for="option in menuOptions"
          :key="option.option"
          :to="{ name: option.routeName }"
          exact
        >
          <v-list-tile-action class="secondary--text">
            <v-icon>{{ option.icon }}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content class="secondary--text">
            <v-list-tile-title>{{ option.text }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data: function() {
    return {
      menuOptions: [
        {
          option: "home",
          text: "Home",
          routeName: "home",
          icon: "home"
        },
        {
          option: "about",
          text: "About",
          routeName: "about",
          icon: "person"
        },
        {
          option: "contact",
          text: "Contact",
          routeName: "contact",
          icon: "email"
        }
      ],
      isDrawOpen: false,
      firstName: "José",
      name: { firstName: "José", lastName: "Coelho" }
    };
  }
};
</script>

<style>
a {
  color: inherit;
  text-decoration: inherit;
}
</style>
