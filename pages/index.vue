<template>
  <v-main>
    <v-container>
      <v-row align="center">
        <v-col class="pt-16" sm="6" no-gutters> 
          <p class="text-lg-h2 text-sm-h3 font-weight-bold ml-16">Hi,</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold ml-16">I'm Rodrigo</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold ml-16">Web Developer</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold ml-16">Web Designer</p>
          <p class="text-lg-h2 text-sm-h3 font-weight-bold ml-16">Pizza lover</p>
          <v-btn raised large class="mt-5 ml-16" elevation="6" color="red">
            Contact
          </v-btn>
          <v-row class="pt-16 ml-16">
            <v-btn icon large>
              <v-icon>mdi-github</v-icon>
            </v-btn>
            <v-btn icon large class="ml-2 mr-2">
              <v-icon>mdi-linkedin</v-icon>
            </v-btn>
            <v-btn icon large>
              <v-icon>mdi-whatsapp</v-icon>
            </v-btn>
          </v-row>
        </v-col>
        <v-col sm="6">
          <!-- Replace the image with one of mine -->
          <v-img contain src="Blogging-bro.svg" class="mr-16"></v-img>
        </v-col>
      </v-row>
    </v-container>
    <v-container class="mt-16">
      <p class="text-center text-h3 text-decoration-underline font-weight-medium red--text">About</p>
      <v-row align="center">
        <v-col sm="6">
          <!-- Replace with another image of me -->
          <v-img src="Creativity-rafiki.svg"></v-img>
        </v-col>
        <v-col sm="6">
          <h2 class="red--text">I'm Rodrigo</h2>
          <p>
            I have 2+ years of experience with programming in general, mostly with web stuff. I'm particulary fond of the back-end but I don't shy away from the front-end. My prefered language is JavaScript, but I also know Python, SQL, PHP and C++.
            <br>I'm fond of challenges and new technologies, so I like to try new stuff all the time, which allows me to broad my view towards other languages, frameworks and libraries and most importantly learn to adapt to new tasks.
            <br>I'm also experienced in using image editors like Photoshop and Ilustrator and UI/UX software like Adobe XD and Figma.
            <br>As far has hobbies go I like to play videogames mostly rpgs and mmos like WoW and FFXIV and read japanese comic books whose number I read is too large for me to count or even estimate. I also like try new kinds of experience in my personal life, mostly food related, but I also love to travel and find more about other cultures and their yummy dishes. 
          </p>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>
