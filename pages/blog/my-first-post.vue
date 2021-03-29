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
        <h2 :class="$vuetify.breakpoint.smAndDown ? 'display-2 font-weight-bold white--text mt-2 mb-2' : 'display-3 font-weight-bold white--text mt-2 mb-1'" align="center">My First Post - Blog #0</h2>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pb-4 pt-0">
      <v-col cols="10" class="pb-0 pt-0">
        <h2 class="subtitle-1 font-weight-light white--text mt-2 mb-6">Date Posted: <span class="font-weight-bold"> 03-01-21 </span></h2>
      </v-col>
    </v-row>
    
    <hr>
    <v-row justify="center" vertical-align="center" class="grey darken-4">
      <v-col cols="8" class>
        <v-container fill-height fluid class="profile"> 
          <v-img eager contain height="30vh" align="center" justify = "center" src = "/blog-imgs/logo-aa.png"></v-img>
        </v-container>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pt-2 pb-16">
      <v-col cols="10" class="pb-0">
        <p> Just how array indexing starts at 0, this is my first blog: Blog #0. I plan to post the latest projects I have been working on and things I have been learning on this blog. I hope you enjoy the journey along with me. </p>
        <p> Here's code blocks for testing purposes: </p>
        <pre><code v-highlight class="python" color="black">import anish-life</code><code v-highlight class="python" color="black">date = "03/01/21"</code><code v-highlight class="python" color="black">anish-life.blog_start(date)</code></pre>


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