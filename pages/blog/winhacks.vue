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
        <h2 :class="$vuetify.breakpoint.smAndDown ? 'display-2 font-weight-bold white--text mt-2 mb-2' : 'display-3 font-weight-bold white--text mt-2 mb-1'" align="center">Winning WinHacks 2021</h2>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pb-4 pt-0">
      <v-col cols="10" class="pb-0 pt-0">
        <h2 class="subtitle-1 font-weight-light white--text mt-2 mb-6">Date Posted: <span class="font-weight-bold"> 03-29-21 </span></h2>
      </v-col>
    </v-row>
    
    <hr>
    <v-row justify="center" vertical-align="center" class="grey darken-4">
      <v-col cols="8" class>
        <v-container fill-height fluid class="profile"> 
          <v-img eager contain height="30vh" align="center" justify = "center" src = "/blog-imgs/winhacks.png"></v-img>
        </v-container>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pt-2 pb-16">
      <v-col cols="10" class="pb-0 post-content">
        <p> During the weekend, I competed in the University of Windsor's <a href="https://winhacks.ca/">WinHacks 2021</a> where my team and I made ChatSpace VR. ChatSpace VR is essentially a space in VR that allows for proximity chat with others. The app also holds three recreational games: Air Hockey, Table Tennis, and 8-Ball Pool. We really struggled in the first few hours to use the right technology. At first, we tried using Oculus, but the black screen issue that stopped the installation of the Oculus app stopped us from making progress. In the end, my team used the Windows Mixed Reality Headsets in Unity to make ChatSpace VR. We had many more network issues and compatability issues, but in the end, we were able to make an app that one the $1000 prize for making a Virtual Society for Mental Health.</p>
        <p>For the complete submission of our project, visit our <a href="https://devpost.com/software/chatspace-vr">devpost</a>. For the source code, visit our <a href="https://github.com/Breality/ChatSpace-VR">github repository</a>.</p>
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
        }),
    }
</script>

<style scoped>
  .post-content a {
    color: #adc0ffec;
    text-decoration: none;
  }
  .post-content a:hover {
    text-decoration: underline;
  }
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