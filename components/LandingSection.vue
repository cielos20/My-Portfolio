<template>
  <v-container class="mt-16 pt-lg-4">
      <v-row justify="center" class="mt-16">
        <p class="font-weight-black text-lg-h2 text-sm-h4">Full-Stack Developer, Designer & Student</p>
      </v-row>
      <v-row justify="center">
        <p class="text-h6 font-weight-medium">I design and code awesome web experiences, and I love what I do.</p>
      </v-row>
      <v-row align="center">
        <v-img v-if="$vuetify.theme.dark" src="blog-bro.svg" width="560px" height="560px" contain></v-img>        
        <v-img v-else-if="!$vuetify.theme.dark" src="blog-bro-light.svg" width="560px" height="560px" contain></v-img>        
      </v-row>
      <v-row justify="center" class="mb-lg-16 pb-lg-16">
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