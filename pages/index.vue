<template>
  <v-main>
    <v-container>
      <v-row>
        <v-col class="pt-16" sm="6" no-gutters> 
          <p class="text-lg-h2 text-sm-h3 font-weight-bold">Hi,</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold">I'm Rodrigo</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold">Web Developer</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold">Web Designer</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold">Pizza lover</p>
          <v-btn raised large class="mt-5" elevation="6" color="red">
            Contact
          </v-btn>
          <v-row class="pt-16">
            <v-btn icon large>
              <v-icon>mdi-github</v-icon>
            </v-btn>
            <v-btn icon large>
              <v-icon>mdi-linkedin</v-icon>
            </v-btn>
            <v-btn icon large>
              <v-icon>mdi-whatsapp</v-icon>
            </v-btn>
          </v-row>
        </v-col>
        <v-col sm="6">
          <!-- Replace the image with one of mine -->
          <v-img contain src="icon.png"></v-img>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>
