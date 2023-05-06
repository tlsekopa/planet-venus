<template>
  <v-card >
    <v-layout>
      <v-app-bar>
        <v-col>
        </v-col>
        <v-col>
        </v-col>
        <v-col><h3>Porn Videos</h3></v-col>
        <v-col></v-col>
        <v-col>
          <v-text-field label="Search" append-icon="mdi-magnify" filled outlined></v-text-field>
        </v-col>
      </v-app-bar>
      <v-navigation-drawer
        expand-on-hover
        rail
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
            title="Sandra Adams"
            subtitle="sandra_a88@gmailcom"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-folder" title="My Items" value="myitems"></v-list-item>
          <v-list-item prepend-icon="mdi-account-multiple" title="Shared with me" value="shared"></v-list-item>
          <v-list-item prepend-icon="mdi-star" title="Starred" value="starred"></v-list-item>
        </v-list>
        <template v-slot:append>
          <div class="pa-2">
            <v-btn block color="error" >
              <v-icon>mdi-logout</v-icon>
            </v-btn>
          </div>
        </template>
      </v-navigation-drawer>
      <v-main style="min-height: 300px;">
        <comp-tabs></comp-tabs>
      </v-main>
    </v-layout>
  </v-card>
</template>

<script>
import CompTabs from './CompTabs.vue';
export default {
  name: 'LandingPage',
  components: {CompTabs},
  data () {
    return {
      drawer: false,
      group: null,
      tab: null,
        items: [
          'web', 'shopping', 'videos', 'images', 'news',
        ],
      videoUrl: "https://www.xvideos.com/video76083555/detention_w_ms._del_rio",
      youtubeURL: "",
      result: "",
      xresults: ""
    }
  },
  watch: {
    group() {
      this.drawer = false
    }
  },
  methods: {
    loadURL() {
      const youtubeEmbedTemplate = "https://www.xvideos.com/embedframe/";
      const url = this.youtubeURL.split(
        /(vi\/|v%3D|v=|\/v\/|youtu\.be\/|\/embed\/)/
      );
      console.log("url", url);
      const YId =
        undefined !== url[2] ? url[2].split(/[^0-9a-z_/\\-]/i)[0] : url[0];
      console.log("YId", YId);
      if (YId === url[0]) {
        console.log("not a youtube link");
      } else {
        console.log("it's  a youtube video");
      }
      const topOfQueue = youtubeEmbedTemplate.concat(YId);
      console.log("topOfQueue", topOfQueue);
      this.result = topOfQueue;
      this.youtubeURL = "";
    },
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