<template>
  <div>
    <v-img v-if="$vuetify.theme.dark" src="wave-down.svg" height="200px"></v-img>
    <v-img v-else-if="!$vuetify.theme.dark" src="wave-down-light.svg" height="200px"></v-img>
    <v-container style="margin-top: -200px">
      <v-row justify="center">
        <v-col v-for="item in items" :key="item.title" cols="2">
          <v-card elevation="6" min-height="650px">
            <v-icon x-large color="primary" class="pl-16 ml-13 mt-8">
              {{item.icon}}
            </v-icon>
            <p class="font-weight-medium text-center text-h5 pt-4">{{item.title}}</p>
            <p class="text-center pl-6 pr-6">{{item.titleText}}</p>
            <p class="text-center font-weight-medium text-h6 primary--text">{{item.subtitleOne}}</p>
            <p class="text-center font-weight-regular">
            {{item.subtitleTextOne}}
            </p>
            <p class="text-center font-weight-medium text-h6 primary--text">{{item.subtitleTwo}} </p>
            <p class="text-center font-weight-regular pr-8 pl-8">
              {{item.subtitleTextTwo}}
            </p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script lang="ts">
 export default {
     data: () => ({
         items: [
             {
                 icon: 'mdi-nodejs',
                 title: "Back-end",
                 titleText: 'I enjoy coding the API and the routes, bringing the correct information to the client.',
                 subtitleOne: "Languages I speak:",
                 subtitleTextOne: 'PHP, Python, SQL',
                 subtitleTwo: 'Server tech I use:',
                 subtitleTextTwo: 'NodeJS, Express, Deno, Django, Flask, Postgres, Firebase, MongoDB',
             },
             {
                 icon: 'mdi-pencil-ruler',
                 title: "Design",
                 titleText: 'I take pride on cool animations and simple yet effective designs.',
                 subtitleOne: "Mockups I take joy in:",
                 subtitleTextOne: 'UI, Web, App, Mobile, Animations',
                 subtitleTwo: "Tools that I use:",
                 subtitleTextTwo: 'Photoshop, Ilustrator, Figma, XD',
             },
             {
                 icon: 'mdi-xml',
                 title: "Front-end",
                 titleText: 'I find genuine fun in using different frameworks and libraries on new projects.',
                 subtitleOne: "Languages I know:",
                 subtitleTextOne: 'JavaScript, HTML, CSS',
                 subtitleTwo: "Client tech I know:",
                 subtitleTextTwo: 'Bootstrap, SASS, Tailwind, React, Vue, Svelte',
             },
         ]
     })
 }
</script>
