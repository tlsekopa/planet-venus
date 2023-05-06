<template>
    <v-card>
      <v-layout>
        <v-system-bar color="grey-darken-3"></v-system-bar>
  
        <v-navigation-drawer
          color="grey-darken-2"
          permanent
          width="72"
        ></v-navigation-drawer>
  
        <v-navigation-drawer
          color="grey-darken-1"
          permanent
          width="150"
        ></v-navigation-drawer>
  
        <v-app-bar
          color="grey"
          height="48"
          flat
        ></v-app-bar>
  
        <v-navigation-drawer
          color="grey-lighten-1"
          location="right"
          permanent
          width="150"
        ></v-navigation-drawer>
  
        <v-app-bar
          color="grey-lighten-2"
          flat
          height="48"
          location="bottom"
        ></v-app-bar>
        <v-main>
          <v-card>
    <v-tabs
      v-model="tab"
      color="deep-purple-accent-4"
      align-tabs="center"
    >
      <v-tab :value="1">Landscape</v-tab>
      <v-tab :value="2">City</v-tab>
      <v-tab :value="3">Abstract</v-tab>
    </v-tabs>
    <v-window v-model="tab">
      <v-window-item
        v-for="n in 3"
        :key="n"
        :value="n"
      >
        <v-container fluid>
          <v-row>
            <v-col
              v-for="i in 6"
              :key="i"
              cols="12"
              md="4"
            >
              <v-img
                :src="`https://picsum.photos/500/300?image=${i * n * 5 + 10}`"
                :lazy-src="`https://picsum.photos/10/6?image=${i * n * 5 + 10}`"
                aspect-ratio="1"
              ></v-img>
            </v-col>
          </v-row>
        </v-container>
      </v-window-item>
    </v-window>
  </v-card>
            <iframe :src="xresults" frameborder=0 width=510 height=400 scrolling=no allowfullscreen=allowfullscreen></iframe>
        </v-main>
      </v-layout>
    </v-card>
  </template>
  <script>
    export default {
      
      name: 'LandingPage',
      data () {
        return {
          tab: null,
          videoUrl: "https://www.xvideos.com/video76083555/detention_w_ms._del_rio",
          youtubeURL: "",
          result: "",
          xresults: ""
        }
      },
      methods: {
        loadThumbnail(){
          const videoEmbedTemplate = "https://www.xvideos.com/embedframe/";
          const vidUrl = this.videoUrl.split(/video|\//)
          const vidId = undefined !== vidUrl[1] ? vidUrl[1].split(/[^0-9]/i)[0] : vidUrl[0]
          if (vidId === vidUrl[0]) {
            console.log("not video link")
          } else {
            console.log("this is the link")
          }
          const frame = videoEmbedTemplate.concat(vidId)
          this.xresults = frame
        }
        
      }
    }
</script>