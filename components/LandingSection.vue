<template>
  <v-container class="mt-10 pt-lg-4">
      <v-row justify="center" class="mt-sm-16 mt-0">
        <p class="font-weight-black text-lg-h2 text-sm-h3 text-h4 text-center">Full-Stack Developer, Designer & Student</p>
      </v-row>
      <v-row justify="center">
        <p class="text-h7 text-sm-h6 font-weight-medium text-center pl-sm-0 pr-sm-0 pl-4 pr-4">I design and code awesome web experiences, and I love what I do.</p>
      </v-row>
      <v-row align="center" class="mt-n16 mt-sm-0">
        <v-img v-if="$vuetify.theme.dark" src="blog-bro.svg" width="560px" height="560px" contain></v-img>        
        <v-img v-else-if="!$vuetify.theme.dark" src="blog-bro-light.svg" width="560px" height="560px" contain></v-img>        
      </v-row>
      <v-row justify="center" class="mb-lg-16 pb-lg-16 mt-n16 mt-sm-0">
        <v-icon color="grey" class="blink">mdi-mouse-move-down</v-icon>
        <p class="grey--text pt-4 pl-2 blink">Keep scrolling...</p>
      </v-row>
    </v-container>
</template>

<style scoped>
  .blink {
    animation: blink 2s ease-in-out infinite;
  }
  @keyframes blink {
    50% {
      opacity: 0.3;
    }
  }
</style>