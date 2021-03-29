<template>
  <v-app color="white">
    <v-app-bar fixed app dense :color = appNavColor :absolute = appNavPos> <!--black / remove abs -->
        <v-tabs centered center color="white" hide-slider show-arrows>
            <v-tabs-slider></v-tabs-slider>
            <v-tab color="white" key="first" :ripple="true" target ="self" href="/">Home</v-tab>
            <v-tab color="white" key="second" :ripple="true" @click="$vuetify.goTo('#blog')">Blog</v-tab>
            <v-tab color="white" key="third" :ripple="true" target="blank" href="/Anish_Aggarwal_Resume.pdf">Resume</v-tab>
        </v-tabs>
    </v-app-bar>
    <v-img
        src = "/bkg_overlay.gif" 
        eager
        height="100vh"
        class="mb-0"
        id = "home">
        <v-overlay absolute color = "black" opacity = "0.75" v-waypoint="{ active: true, callback: onWaypoint, options: intersectionOptions }">
          <v-img src = "/profile.png" contain height = "30vh"></v-img>
          <br>
          <v-row>
            <v-col align = "center">
              <h1 class = "pb-2 display-2 font-weight-medium">
                Hi. Welcome to my blog.
              </h1>
              <h3 class = "headline font-weight-regular">
                Here, I will post about my latest insights. Scroll down to see more.
              </h3>
            </v-col>
          </v-row>
        </v-overlay>
    </v-img>

    <v-row justify="center" align="center" class="white pt-16 pb-0">
      <v-col cols="12" class="pb-0">
        <h2 class="display-3 font-weight-bold black--text mt-2 mb-6" id="blog" align="center">My Blog</h2>
      </v-col>
    </v-row>
    <v-row v-for="a in articles" v-bind:key="a.title" justify="center" align="center" class = "d-flex flex-wrap align-content-space-around white pt-5 pl-5 pr-0 pb-16 ma-0">
      <v-col :cols = "$vuetify.breakpoint.smAndDown ? '12' : '8'"  class = "pb-0">
      <a target = "self" class="blog-post" :href ="a.link">
        <v-card elevation="2" outlined color="black" class="blog-post">
          <v-list-item four-line class="pr-0">
            <v-list-item-content>

              <div class="overline mb-4 category">
                {{a.category}}
              </div>
              <v-list-item-title :class="$vuetify.breakpoint.smAndDown ? 'title mb-1 mt-0 font-weight-bold' : 'headline mb-1 mt-0 font-weight-bold'">
                {{a.title}}
              </v-list-item-title>
              <v-list-item-subtitle :class="$vuetify.breakpoint.smAndDown ? 'subtitle-2' : ''">{{a.description}}</v-list-item-subtitle>
              <div class="overline mt-4">
                Date Posted: {{a.date}}
              </div>
            </v-list-item-content>

            <v-list-item-avatar
              tile
              :size="$vuetify.breakpoint.smAndDown ? '70': '150'"
              color='transparent'
              class = "pa-0 my-0 ml-5 mr-5"
            >
            <v-img src="/blog-imgs/logo-aa.png" class="rounded"></v-img>
            </v-list-item-avatar>
          </v-list-item>

        </v-card>
      </a>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="white pt-16 ma-0 pb-0">
      <v-col cols="12" class="pb-0">
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="white pt-10 ma-0 pb-0">
      <v-col cols="12" class="pb-0">
      </v-col>
    </v-row>
    <v-container class="pa-12"></v-container>
    <v-footer padless app absolute>
          <v-card
        flat
        tile
        width="100%"
        class="black lighten-1 white--text text-center"
      >
        <v-card-text>
          <v-hover v-slot="{hover}" v-for="(icon,index) in icons"
              :key="index">
            <v-btn
              class="mx-4 white--text pa-6"
              icon
              :href="icon.link"
              target="blank"
            >
            <v-icon :size="hover? '35px' : '24px'">
              {{ icon.type }}
            </v-icon>
          </v-btn>
          </v-hover>
          
        </v-card-text>

        <v-card-text class="white--text pt-0">
          &lt;/&gt; made with &#128151; and &#127925;
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Anish Aggarwal</strong>
        </v-card-text>
      </v-card>

      </v-footer>
  </v-app>
</template>

<script>
    export default {
        mounted() {
        },
        data: () => ({
            appNavColor: "transparent",
            appNavPos: true,
            changeCount: 1,
            curCount: 0,
            navBarMode: 0,
            intersectionOptions: {
              root: null,
              rootMargin: '20px 0px 0px 0px',
              threshold: [0, 1] // [0.25, 0.75] if you want a 25% offset!
            },
            icons: [
                    {type: 'mdi-facebook', link: 'https://www.facebook.com/aaggarwal10'},
                    {type: 'mdi-linkedin', link: 'https://www.linkedin.com/in/aaggarwal10/'},
                    {type: 'mdi-instagram', link: 'https://www.instagram.com/anish_a10/'},
                    {type: 'mdi-github', link: 'https://github.com/aaggarwal10'},
                    {type: 'mdi-email', link: "mailto:hello@anishaggarwal.ca"}
                  ],
            articles: [
                        {title: "My First Post - Blog #0", date: "01 March 2021", description: "The start of the life of my blog.", category: "Miscellaneous", img:"/blog-imgs/logo-aa.png", link: "/blog/my-first-post"}
            ]
        }),
    methods: {
        onWaypoint ({ going, direction }) {
        // going: in, out
        // direction: top, right, bottom, left
        if (going === this.$waypointMap.GOING_IN) {
            if (this.navBarMode && this.curCount >= this.changeCount){
            this.appNavColor = "transparent"
            this.appNavPos = true
            } else if (!this.navBarMode){
            this.navBarMode = true
            this.curCount = 1
            } else{
            this.curCount += 1
            }
            console.log('waypoint going in!')
        }
    
        if (direction === this.$waypointMap.DIRECTION_TOP) {
            console.log("HERE")
            
            console.log((this.navBarMode == false) && (this.curCount == this.changeCount))
            if ((!this.navBarMode) && (this.curCount == this.changeCount)){
            console.log("Here1")
            this.appNavColor = "black"
            this.appNavPos = false
            } else if (this.navBarMode){
            this.navBarMode = false
            this.curCount = 1
            } else{
            this.curCount += 1
            }
            console.log('waypoint going top!')
        }
        }
    }
}
</script>
<style scoped>
.category{
  text-decoration: underline;
  color: rgb(157, 205, 208);
}
.rounded{
    border-radius:20px;
}
.blog-post:hover {
  transform: scale(1.01); /* (150% zoom - Note: if the zoom is too large, it will go outside of the viewport) */
}
a.blog-post{
  text-decoration:none;
}
</style>