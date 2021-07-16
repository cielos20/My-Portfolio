<template>
  <v-app>
    <v-app-bar app elevate-on-scroll color="secondary">
        <p class="text-h5 pt-3 ml-lg-16">Rodrigo</p>
        <v-spacer ></v-spacer>
        <v-btn text>Contact</v-btn>
        <v-btn text>Blog</v-btn>
        <v-btn icon class="mr-16" :color="$vuetify.theme.dark ? 'yellow' : 'blue'" @click="$vuetify.theme.dark=!$vuetify.theme.dark" >
          <v-icon  v-if="$vuetify.theme.dark===true">mdi-weather-sunny</v-icon>
          <v-icon  v-if="$vuetify.theme.dark===false">mdi-weather-night</v-icon>
        </v-btn>
    </v-app-bar>
    <Nuxt />
  </v-app>
</template>


