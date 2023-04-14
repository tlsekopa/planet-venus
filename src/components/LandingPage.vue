<template>
  <v-card>
    <v-layout>
      <v-app-bar color="surface-variant" title="Planet Venus"><img src="../assets/planet_venus.jpg" alt=""></v-app-bar>
        <v-carousel hide-delimiters>
          <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
          ></v-carousel-item>
        </v-carousel>
      <v-main style="min-height: 300px;"></v-main>
    </v-layout>
  </v-card>
</template>

<script>
export default {
  name: 'LandingPage',
  data () {
    return {
      items: [
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
        }
      ]
    }
  }
}
</script>