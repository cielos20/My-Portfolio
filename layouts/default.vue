<template>
  <v-app>
    <v-app-bar app elevate-on-scroll color="secondary">
        <p class="text-sm-h5 text-h6 pt-3 ml-lg-16">
          <nuxt-link class="text-decoration-none white--text" to="/">Rodrigo</nuxt-link>
        </p>
        <v-spacer ></v-spacer>
        <v-btn link class="mr-2">
          <nuxt-link class="text-decoration-none" to="/contact">Contact</nuxt-link>
        </v-btn>
        <v-btn link class="mr-2">
          <nuxt-link class="text-decoration-none" to="/blog">Blog</nuxt-link>
        </v-btn>
        <v-btn icon class="mr-sm-16 mr-2" :color="$vuetify.theme.dark ? 'yellow' : 'blue'" @click="$vuetify.theme.dark=!$vuetify.theme.dark" >
          <v-icon  v-if="$vuetify.theme.dark===true">mdi-weather-sunny</v-icon>
          <v-icon  v-if="$vuetify.theme.dark===false">mdi-weather-night</v-icon>
        </v-btn>
    </v-app-bar>
    <Nuxt />
  </v-app>
</template>

