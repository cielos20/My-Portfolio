<template>
  <div>
    <v-container class="mt-16 pt-lg-4">
      <v-row justify="center" class="mt-16">
        <p class="font-weight-black text-lg-h2 text-sm-h4">Full-Stack Developer, Designer & Student</p>
      </v-row>
      <v-row justify="center">
        <p class="text-h6 font-weight-medium">I design and code awesome web experiences, and I love what I do.</p>
      </v-row>
      <v-row align="center">
        <v-img src="blog-bro.svg" width="400px" height="400px" contain></v-img>        
      </v-row>
      <v-row justify="center" class="mb-lg-16 pb-lg-16">
        <v-icon color="grey">mdi-mouse-move-down</v-icon>
        <p class="grey--text pt-4 pl-2">Keep scrolling...</p>
      </v-row>
    </v-container>
    <!-- Make a keep scrolling arrow and text animation like blinking-->
    <v-container class="red mt-lg-16" fluid>
      <v-row justify="center" class="pt-16 pb-16 pl-16 pr-16">
          <h2 class="pb-5">Hello. I'm Rodrigo. Nice to know you.</h2>
          <p>
            I have 2+ years of experience with programming in general, mostly with web stuff. I'm particulary fond of the back-end but I don't shy away from the front-end. My prefered language is JavaScript, but I also know Python, SQL, PHP and C++.
            <br>I'm fond of challenges and new technologies, so I like to try new stuff all the time, which allows me to broad my view towards other languages, frameworks and libraries and most importantly learn to adapt to new tasks.
            <br>I'm also experienced in using image editors like Photoshop and Ilustrator and UI/UX software like Adobe XD and Figma.
            <br>As far has hobbies go I like to play videogames mostly rpgs and mmos like WoW and FFXIV and read japanese comic books whose number I read is too large for me to count or even estimate. I also like try new kinds of experience in my personal life, mostly food related, but I also love to travel and find more about other cultures and their yummy dishes. 
          </p>
      </v-row>
      <v-row class="red mt-16 mb-16 pt-16 pb-16"></v-row>
    </v-container>
    <v-container style="margin-top: -100px">
      <v-row justify="center">
        <v-col cols="2">
          <v-card elevation="6" min-height="650px">
            <v-icon large color="red" class="pl-16 ml-14 mt-8">
              mdi-nodejs
            </v-icon>
            <p class="font-weight-medium text-center text-h5 pt-4">Back-end</p>
            <p class="text-center pl-6 pr-6">I enjoy coding the API and the routes, bringing the correct information to the client.</p>
            <p class="text-center font-weight-medium text-h6 red--text">Languages I speak:</p>
            <p class="text-center font-weight-regular">
              PHP<br>
              Python<br>
              SQL<br>
            </p>
            <p class="text-center font-weight-medium text-h6 red--text">Server tech I use:</p>
            <p class="text-center font-weight-regular">
              NodeJS<br>
              Express<br>
              Deno<br>
              Django<br>
              Flask<br>
              Postgres<br>
              Firebase<br>
              MongoDB<br>
            </p>
          </v-card>
        </v-col>
        <v-col cols="2">
          <v-card elevation="6" min-height="650px">
            <v-icon large color="red" class="pl-16 ml-14 mt-8">
              mdi-pencil-ruler
            </v-icon>
            <p class="font-weight-medium text-center text-h5 pt-4">Design</p>
            <p class="text-center pl-6 pr-6">I take pride on cool animations and simple yet effective designs.</p>
            <p class="text-center font-weight-medium text-h6 red--text">Mockups I take joy in:</p>
            <p class="text-center font-weight-regular">
              UI, Web, App, Mobile, Animations
            </p>
            <p class="text-center font-weight-medium text-h6 red--text">Tools that I use:</p>
            <p class="text-center font-weight-regular">
              Photoshop<br>
              Ilustrator<br>
              Figma<br>
              XD<br>
            </p>
          </v-card>
        </v-col>
        <v-col cols="2">
          <v-card elevation="6" min-height="650px">
            <v-icon large color="red" class="pl-16 ml-14 mt-8">
              mdi-xml
            </v-icon>
            <p class="font-weight-medium text-center text-h5 pt-4">Front-end</p>
            <p class="text-center pl-6 pr-6">I find genuine fun in using different frameworks and libraries on new projects.</p>
            <p class="text-center font-weight-medium text-h6 red--text">Languages I know:</p>
            <p class="text-center font-weight-regular">
              JavaScript<br>
              HTML<br>
              CSS<br>
            </p>
            <p class="text-center font-weight-medium text-h6 red--text">Client tech I know:</p>
            <p class="text-center font-weight-regular">
              Bootstrap<br>
              Material Design<br>
              SASS<br>
              Tailwind<br>
              React<br>
              Vue<br>
              Svelte<br>
            </p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
