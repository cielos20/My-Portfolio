<template>
    <v-container v-resize="onResize" class="mt-16 pt-16 mb-16">
      <p class="text-center text-h3">My projects</p>
      <p class="text-center text-break">This a list of my projects. Like what you see try and contact me<span class="primary--text"> here</span></p>
      <v-row class="mt-16 pt-16" justify="center">
        <v-col v-for="item in items" :key="item.title" cols="10" md="4">
        <!-- Need to check how to trigger hover effects on mobile -->
        <div v-if="windowSize.x <= 700">
          <v-card>
              <v-img :src="item.img" height="320px"></v-img>
                  <v-card-title class="text-break">{{item.title}}</v-card-title>
                  <v-col cols="12">
                    <v-btn outlined color="white" elevation="1" class="ml-8" to="{{item.link}}">See the website</v-btn>
                  </v-col> 
            </v-card>
        </div>
        <div v-else>
          <v-hover v-slot="{hover}">
            <v-card >
              <v-img :src="item.img" height="320px">
                <v-expand-transition>
                  <div v-if="hover" class="d-flex transition-fast-in-fast-out primary text--text" style="height: 100%">
                    <v-row align-content="center">
                      <v-col cols="12">
                      <p class="text-h3 text-lg-h4 pl-8 pr-8">{{item.title}}</p>
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
        </div>
        </v-col>
      </v-row>
    </v-container>
</template>

<script>
 export default {
     data: () => ({
         items: [
             {
                 img: 'absolutauge.png',
                 title: "Absolutauge's newest portfolio website in wordpress",
                 link: 'https://absolutauge.vonchronoshaus.com/',
             },
             {
                 img: 'undraw-coming-soon.svg',
                 title: "Florista de São Marcos a woocommerce flowershop. Coming soon...",
                 link: '#',
             },
         ],
         windowSize: {
           x: 0,
           y: 0
         }
     }),
     mounted() {
       this.onResize()
     },
     methods: {
          onResize() {
            this.windowSize = {x: window.innerWidth, y: window.innerHeight}
          }
      },
 }
</script>
