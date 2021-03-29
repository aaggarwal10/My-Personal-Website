<template>
  <v-app>
    <nuxt />
  </v-app>
  </template>
    <!--<v-main class="pa-0">
      <v-app-bar fixed app absolute dense color="transparent">
      <v-tabs right v-model="tabs" color="white" hide-slider>
        <v-tab :ripple="true" nuxt to="/">Home</v-tab>
        <v-tab :ripple="true" @click="$vuetify.goTo('#about')">About</v-tab>
        <v-tab :ripple="true" @click="$vuetify.goTo('#skills')">Skills</v-tab>
        <v-tab :ripple="true" @click="$vuetify.goTo('#projects')">Projects</v-tab>
        <v-tab :ripple="true" @click="$vuetify.goTo('#experience')">Experience</v-tab>
        <v-tab :ripple="true" @click="$vuetify.goTo('#skills')">Blog</v-tab>
        <v-tab :ripple="true" target="blank" href="/resume...">Resume</v-tab>
      </v-tabs>
      </v-app-bar> 
      
      <v-app-bar dense color="black" inverted-scroll scroll-target="#scrolling-techniques-8" scroll-threshold="700">
        <v-tabs right color="white" hide-slider>
          <v-tab :ripple="true" nuxt to="/">Home</v-tab>
          <v-tab :ripple="true" @click="$vuetify.goTo('#about')">About</v-tab>
          <v-tab :ripple="true" @click="$vuetify.goTo('#skills')">Skills</v-tab>
          <v-tab :ripple="true" @click="$vuetify.goTo('#projects')">Projects</v-tab>
          <v-tab :ripple="true" @click="$vuetify.goTo('#experience')">Experience</v-tab>
          <v-tab :ripple="true" @click="$vuetify.goTo('#skills')">Blog</v-tab>
          <v-tab :ripple="true" target="blank" href="/resume...">Resume</v-tab>
        </v-tabs>
      </v-app-bar>
      
      <v-container
           id="scrolling-techniques-8"
            max-height="100vh"> 
      </v-container>

      
      
  </v-app>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      is_transparent: true
    }
  },
  methods: {
    onScroll(e) {
      this.is_transparent = !(e.target.scrollTop > 0);
    }
  },
}
</script>
