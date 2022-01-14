<template>
  <div>
    <v-app color="black">
    <v-app-bar fixed app dense color = "black"> <!--black / remove abs -->
        <v-tabs centered color="white" hide-slider show-arrows>
            <v-tabs-slider></v-tabs-slider>
            <v-tab :ripple="true" target ="self" href="/">Home</v-tab>
            <v-tab :ripple="true" target = "self" href = "/blog">Blog</v-tab>
            <v-tab :ripple="true" target="blank" href="/Anish_Aggarwal_Resume.pdf">Resume</v-tab>
        </v-tabs>
    </v-app-bar>
    <v-row class="grey darken-4">
      <v-col cols="10" class="pb-0 pt-16 pl-5">
        <router-link to="/blog" style="text-decoration: none">
        <v-btn
          outlined
          link>
          Back
        </v-btn>
        </router-link>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pb-0">
      <v-col cols="10" class="pb-0">
        <h2 :class="$vuetify.breakpoint.smAndDown ? 'display-2 font-weight-bold white--text mt-2 mb-2' : 'display-3 font-weight-bold white--text mt-2 mb-1'" align="center">Winning the Spatial Annual Hackathon</h2>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pb-4 pt-0">
      <v-col cols="10" class="pb-0 pt-0">
        <h2 class="subtitle-1 font-weight-light white--text mt-2 mb-6">Date Posted: <span class="font-weight-bold"> 01-07-22 </span></h2>
      </v-col>
    </v-row>
    
    <hr>
    <v-row justify="center" vertical-align="center" class="grey darken-4">
      <v-col cols="8" class>
        <v-container fill-height fluid class="profile"> 
          <v-img eager contain height="30vh" align="center" justify = "center" src = "/blog-imgs/animationTimeline.png"></v-img>
        </v-container>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pt-2 pb-16">
      <v-col cols="10" class="pb-0">
        <p> The video for this project can be found on youtube at <a href="https://youtu.be/Zi4cYGgL0qY">this link</a>.
        <p> Over the course of my final week at Spatial, I took part in a company hackathon. The video above is the Animation Timeline Editor that my team created. This app was built on top of the existing Spatial application. My team and I created an Animation Timeline Editor that allows users to take a snapshot of the room. Each snapshot could then be transitioned between using various different state transitions as shown in the video above.</p>
        <p> I worked on the backend and state architecture of the application. This includes the functionality of changing the scene to match the given timeline when the animator is playing and networking all of the animation actions to all clients. Furthermore, I created the transitional function for calculating the state values depending on the time between state snapshots. Overall, I had a great time working with fellow interns to develop a functioning hack.</p>
        <p> In the end, our team ended up WINNING 2 of the 5 prizes presented in the hackathon which were the CEOs' Choice Award and the User's Choice Award. We also came in as a runner-up for the People's Choice Award making us one of the big winners for the hackathon. The experience really made for a fantastic end to my first internship working for Spatial. I could not have asked for more as a first internship. </p>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pt-10 ma-0 pb-0">
      <v-col cols="12" class="pa-0">
      </v-col>

    </v-row>

    <v-container class="pa-10"></v-container>
    <v-container class="pa-11"></v-container>
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
    
  </div>
</template>

<script>
    export default {
        data: () => ({
            icons: [
                    {type: 'mdi-facebook', link: 'https://www.facebook.com/aaggarwal10'},
                    {type: 'mdi-linkedin', link: 'https://www.linkedin.com/in/aaggarwal10/'},
                    {type: 'mdi-instagram', link: 'https://www.instagram.com/anish_a10/'},
                    {type: 'mdi-github', link: 'https://github.com/aaggarwal10'},
                    {type: 'mdi-email', link: "mailto:hello@anishaggarwal.ca"}
                  ],
        })

    }
</script>

<style scoped>
  code {
      background-color: rgb(0,0,0,1);
      color: #f8f8f2;
      border-radius: 0.3rem;
      padding: 4px 1px 1px 10px;
      white-space: nowrap;
  }

  pre {
    background-color: #000000;
    color: white;
    border-radius: 0.3em;
    border: 1px solid #aaa9ad;
    padding: 0px 0px 5px 0px;
    height: "3vh";
  }

  pre code {
    white-space: pre;
  }
  p{
    color: white;
  }
</style>