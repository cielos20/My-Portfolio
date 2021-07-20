<template>
  <v-app>
    <v-app-bar app elevate-on-scroll color="secondary" class="hidden-xs-and-down">
        <p class="text-sm-h5 text-h6 pt-3 ml-lg-16">
          <nuxt-link class="text-decoration-none primary--text" to="/">Rodrigo</nuxt-link>
        </p>
        <v-spacer ></v-spacer>
        <Search class="mt-7 mr-16" />
        <v-btn link class="mr-2">
          <nuxt-link class="text-decoration-none" to="/contact">Contact</nuxt-link>
        </v-btn>
        <v-btn link class="mr-2">
          <nuxt-link class="text-decoration-none" to="/blog">Blog</nuxt-link>
        </v-btn>
        <v-btn icon class="mr-sm-16 mr-2" :color="$vuetify.theme.dark ? 'yellow' : 'blue'" @click="$vuetify.theme.dark=!$vuetify.theme.dark" >
          <v-icon v-if="$vuetify.theme.dark===true">mdi-weather-sunny</v-icon>
          <v-icon v-if="$vuetify.theme.dark===false">mdi-weather-night</v-icon>
        </v-btn>
    </v-app-bar>
    <v-app-bar app elevate-on-scroll color="secondary" class="hidden-sm-and-up">
      <v-toolbar-title>Rodrigo</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group v-model="group" active-class="primary--text">
          <v-list-item>
            <v-btn link class="mr-2">
              <nuxt-link class="text-decoration-none" to="/contact">Contact</nuxt-link>
            </v-btn>
          </v-list-item>
          <v-list-item>
            <v-btn link class="mr-2">
               <nuxt-link class="text-decoration-none" to="/blog">Blog</nuxt-link>
            </v-btn>
          </v-list-item>
          <v-list-item>
            <v-btn icon class="mr-sm-16 mr-2" :color="$vuetify.theme.dark ? 'yellow' : 'blue'" @click="$vuetify.theme.dark=!$vuetify.theme.dark" >
              <v-icon v-if="$vuetify.theme.dark===true">mdi-weather-sunny</v-icon>
              <v-icon v-if="$vuetify.theme.dark===false">mdi-weather-night</v-icon>
            </v-btn>
          </v-list-item>
        </v-list-item-group>
      </v-list>  
    </v-navigation-drawer>
    <Nuxt />
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null
  }),
  watch: {
    group() {
      this.drawer = false
    }
  }
}
</script>