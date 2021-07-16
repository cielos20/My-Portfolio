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
        <v-img v-if="$vuetify.theme.dark" src="blog-bro.svg" width="560px" height="560px" contain></v-img>        
        <v-img v-else-if="!$vuetify.theme.dark" src="blog-bro-light.svg" width="560px" height="560px" contain></v-img>        
      </v-row>
      <v-row justify="center" class="mb-lg-16 pb-lg-16">
        <v-icon color="grey" class="blink">mdi-mouse-move-down</v-icon>
        <p class="grey--text pt-4 pl-2 blink">Keep scrolling...</p>
      </v-row>
    </v-container>
    <v-img v-if="$vuetify.theme.dark" src="wave.svg" height="300px" class="mt-16"></v-img>
    <v-img v-else-if="!$vuetify.theme.dark" src="wave-light.svg" height="300px" class="mt-16"></v-img>
    <v-container class="primary text--text" fluid>
      <v-row justify="center" class="pt-16 pb-16 pl-16 pr-16">
          <h2 class="pb-5">Hello. I'm Rodrigo. Nice to know you.</h2>
          <p class="pl-16 pr-16">
            I have 2+ years of experience with programming in general, mostly with web stuff. I'm particulary fond of the back-end but I don't shy away from the front-end. My prefered language is JavaScript, but I also know Python, SQL, PHP and C++.
            <br>I'm fond of challenges and new technologies, so I like to try new stuff all the time, which allows me to broad my view towards other languages, frameworks and libraries and most importantly learn to adapt to new tasks.
            <br>I'm also experienced in using image editors like Photoshop and Ilustrator and UI/UX software like Adobe XD and Figma.
            <br>As far has hobbies go I like to play videogames mostly rpgs and mmos like WoW and FFXIV and read japanese comic books whose number I read is too large for me to count or even estimate. I also like try new kinds of experience in my personal life, mostly food related, but I also love to travel and find more about other cultures and their yummy dishes. 
          </p>
      </v-row>
      <v-row class="primary mt-16 pt-16"></v-row>
    </v-container>
    <v-img v-if="$vuetify.theme.dark" src="wave-down.svg" height="200px"></v-img>
    <v-img v-else-if="!$vuetify.theme.dark" src="wave-down-light.svg" height="200px"></v-img>
    <v-container style="margin-top: -200px">
      <v-row justify="center">
        <v-col cols="2">
          <v-card elevation="6" min-height="650px">
            <v-icon x-large color="primary" class="pl-16 ml-13 mt-8">
              mdi-nodejs
            </v-icon>
            <p class="font-weight-medium text-center text-h5 pt-4">Back-end</p>
            <p class="text-center pl-6 pr-6">I enjoy coding the API and the routes, bringing the correct information to the client.</p>
            <p class="text-center font-weight-medium text-h6 primary--text">Languages I speak:</p>
            <p class="text-center font-weight-regular">
              PHP<br>
              Python<br>
              SQL<br>
            </p>
            <p class="text-center font-weight-medium text-h6 primary--text">Server tech I use:</p>
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
            <v-icon x-large color="primary" class="pl-16 ml-13 mt-8">
              mdi-pencil-ruler
            </v-icon>
            <p class="font-weight-medium text-center text-h5 pt-4">Design</p>
            <p class="text-center pl-6 pr-6">I take pride on cool animations and simple yet effective designs.</p>
            <p class="text-center font-weight-medium text-h6 primary--text">Mockups I take joy in:</p>
            <p class="text-center font-weight-regular">
              UI, Web, App, Mobile, Animations
            </p>
            <p class="text-center font-weight-medium text-h6 primary--text">Tools that I use:</p>
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
            <v-icon x-large color="primary" class="pl-16 ml-13 mt-8">
              mdi-xml
            </v-icon>
            <p class="font-weight-medium text-center text-h5 pt-4">Front-end</p>
            <p class="text-center pl-6 pr-6">I find genuine fun in using different frameworks and libraries on new projects.</p>
            <p class="text-center font-weight-medium text-h6 primary--text">Languages I know:</p>
            <p class="text-center font-weight-regular">
              JavaScript<br>
              HTML<br>
              CSS<br>
            </p>
            <p class="text-center font-weight-medium text-h6 primary--text">Client tech I know:</p>
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
    <v-container class="mt-16 pt-16 mb-16">
      <p class="text-center text-h3">My projects</p>
      <p class="text-center">This a list of my projects. Like what you see try and contact me<span class="primary--text"> here</span></p>
      <v-row class="mt-16 pt-16">
        <v-col cols="4">
          <v-hover v-slot="{hover}">
            <!-- Figure how to make it overlay on hover on the card -->
            <v-card >
              <v-img src="pc-bro.jpg" max-height="320px">
                <v-expand-transition>
                  <div v-if="hover" class="d-flex transition-fast-in-fast-out primary text--text" style="height: 100%">
                    <v-row align-content="center">
                      <v-col cols="12">
                      <p class="text-h3 pl-8">Absolutauge's newest portfolio website in wordpress</p>
                      </v-col>
                      <v-col cols="12">
                        <v-btn outlined color="white" elevation="1" class="ml-8">See the website</v-btn>
                      </v-col>
                    </v-row>
                  </div>
                </v-expand-transition>
              </v-img>
            </v-card>
          </v-hover>
        </v-col>
        <v-col cols="4">
          <v-hover v-slot="{hover}">
            <!-- Figure how to make it overlay on hover on the card -->
            <v-card>
              <v-img src="soccer.jpg" max-height="320px">
                <v-expand-transition>
                  <div v-if="hover" class="d-flex transition-fast-in-fast-out primary text--text" style="height: 100%;">
                    <v-row align-content="center">
                      <v-col cols="12">
                      <p class="text-h3 pl-8">Vonchronoshaus a website about a dog breeder and it's puppies</p>
                      </v-col>
                      <v-col cols="12">
                        <v-btn outlined color="white" elevation="1" class="ml-8">See the website</v-btn>
                      </v-col>
                    </v-row>
                  </div>
                </v-expand-transition>
              </v-img>
            </v-card>
          </v-hover>
        </v-col>
        <v-col cols="4">
          <v-hover v-slot="{hover}">
            <!-- Figure how to make it overlay on hover on the card -->
            <v-card>
              <v-img src="https://cdn.vuetifyjs.com/images/cards/forest-art.jpg">
                <v-expand-transition>
                  <div v-if="hover" class="d-flex transition-fast-in-fast-out primary text--text" style="height: 100%">
                    <v-row align-content="center">
                      <v-col cols="12">
                        <p class="text-h3 pl-8 pr-8">Florista de São Marcos a woocommerce flowershop</p>
                      </v-col>
                      <v-col cols="12">
                        <v-btn outlined color="white" elevation="1" class="ml-8">See the website</v-btn>
                      </v-col>
                    </v-row>
                  </div>
                </v-expand-transition>
              </v-img>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
    <!-- Make a footer with contact prob -->
    <v-img v-if="$vuetify.theme.dark" src="wave.svg" height="300px" class="mt-16"></v-img>
    <v-img v-else-if="!$vuetify.theme.dark" src="wave-light.svg" height="300px" class="mt-16"></v-img>
    <v-container class="primary" fluid>
      <v-row justify="center">
        <v-col cols="6" class="text-center pl-16 pr-16 text--text">
          <p class="text-h4 font-weight-medium ">Like what you see? <br>Wanna have a chat? <br>I'll buy the coffee.</p>
          <p class="text-h6 font-weight-light ">Have a job you would like to offer?</p>
          <v-btn color="white" outlined elevation="1" class="mb-16">Hire me</v-btn> 
        </v-col>
        <v-col cols="6">
          <v-row justify="center">
            <v-icon class="ml-16 pb-3 pt-n3 pr-2" color="text" large>mdi-email</v-icon>
            <p class="text-h6 text--text">cielos20@hotmail.com</p>
          </v-row>
          <v-row justify="center">
            <v-icon class="ml-n16 pb-3 pt-n3 pr-2" color="text" large>mdi-github</v-icon>
            <p class="text-h6 text--text">cielos20</p>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </div>
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