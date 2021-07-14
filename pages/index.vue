<template>
  <div>
    <v-container class="mt-16">
      <v-row justify="center" class="mt-16">
        <p class="font-weight-black text-lg-h2 text-sm-h4">Full-Stack Developer, Designer & Student</p>
        <p class="text-h6 font-weight-medium">I design and code awesome web experiences, and I love what I do.</p>
      </v-row>
      <v-row align="center">
        <v-img src="blog-bro.svg" width="400px" height="400px" contain></v-img>        
      </v-row>
      <v-row justify="center" class="mb-16">
        <v-icon color="grey">mdi-mouse-move-down</v-icon>
        <p class="grey--text pt-4 pl-2">Keep scrolling...</p>
      </v-row>
    </v-container>
    <!-- Make a keep scrolling arrow and text animation like blinking-->
    <v-container class="red" fluid>
      <v-row align="center" class="pt-16 pb-16 pl-16 pr-16">
          <h2 class="pb-5">Hello. I'm Rodrigo. Nice to know you.</h2>
          <p>
            I have 2+ years of experience with programming in general, mostly with web stuff. I'm particulary fond of the back-end but I don't shy away from the front-end. My prefered language is JavaScript, but I also know Python, SQL, PHP and C++.
            <br>I'm fond of challenges and new technologies, so I like to try new stuff all the time, which allows me to broad my view towards other languages, frameworks and libraries and most importantly learn to adapt to new tasks.
            <br>I'm also experienced in using image editors like Photoshop and Ilustrator and UI/UX software like Adobe XD and Figma.
            <br>As far has hobbies go I like to play videogames mostly rpgs and mmos like WoW and FFXIV and read japanese comic books whose number I read is too large for me to count or even estimate. I also like try new kinds of experience in my personal life, mostly food related, but I also love to travel and find more about other cultures and their yummy dishes. 
          </p>
      </v-row>
    </v-container>
    <v-container>
      <v-row no-gutters>
        <v-col cols="2">
          <v-card elevation="6" min-height="350px">
            <v-card-title>Back-end</v-card-title>
            <v-card-text>
              NodeJS<br>
              Express<br>
              Deno<br>
              PHP<br>
              Python<br>
              Django<br>
              Flask<br>
              SQL<br>
              Postgres<br>
              Firebase<br>
              MongoDB<br>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="2">
          <v-card elevation="6" min-height="350px">
            <v-card-title >Design</v-card-title>
            <v-card-text>
              Photoshop<br>
              Ilustrator<br>
              Figma<br>
              XD<br>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="2">
          <v-card elevation="6" min-height="350px">
            <v-card-title>Front-end</v-card-title>
            <v-card-text>
              JavaScript<br>
              HTML<br>
              CSS<br>
              SASS<br>
              Tailwind<br>
              React<br>
              Vue<br>
              Svelte<br>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
