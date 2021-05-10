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
        <h2 :class="$vuetify.breakpoint.smAndDown ? 'display-2 font-weight-bold white--text mt-2 mb-2' : 'display-3 font-weight-bold white--text mt-2 mb-1'" align="center">My HackKU Experience</h2>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pb-4 pt-0">
      <v-col cols="10" class="pb-0 pt-0">
        <h2 class="subtitle-1 font-weight-light white--text mt-2 mb-6">Date Posted: <span class="font-weight-bold"> 04-15-21 </span></h2>
      </v-col>
    </v-row>
    
    <hr>
    <v-row justify="center" vertical-align="center" class="grey darken-4">
      <v-col cols="8" class>
        <v-container fill-height fluid class="profile">
          <v-img eager contain height="30vh" align="center" justify = "center" src = "/blog-imgs/hackku.png"></v-img>
        </v-container>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pt-2 pb-16">
      <v-col cols="10" class="pb-0 post-content">
        <p> During the weekend, I competed in the  <a href="https://hackku.devpost.com/">University of Kansas's Hackathon</a> where my team and I made Discourse VR. Discourse VR is essentially a space in VR that allows for debate with others. This app is similar to Chatspace VR that I at Winhack VR. However, we expanded on a lot of functionality. For example, we added a playback with audio feature that was uploaded to a web client where speakers could watch their speeches over and improve. Furthermore, we had a spectator client where people could come in and leave comments on what the speakers could improve on. These comments would be time stamped and also uploaded to the server in real time allowing speakers to get feedback on their speeches. Finally, the speeches were timed in standard debate formats giving each speaker appropriate times to speak at.</p>
        <p> Now, onto the "How I Screwed Up" part. So, the thing is in almost every hackathon there is usually a moment in which everything breaks and you start doubting whether you can even complete the hackathon. This moment might be short or long, but it usually happens at some point. For example, during Winhacks, everything we had broke on the first day. It was so bad at one point that we could not even install the Oculus Software we needed for VR. This issue happened on the first day as we were just getting back into VR Development. After overcoming the issue on the first day, everything else was smooth sailing and we were able to complete a pretty decent app (in my opinion) for completetion. </p>
        <p> For this hackathon, our "everything breaks moment" came about 10 hours before the end of the hackathon. About 12 hours before submission, we had our core project done smoothly. However, we kept on wanting to work and make the project better by adding a Transcript Feature with speech to text, but at that moment everything started breaking. The worst part is that it did not just completely break. Our project worked sometimes and did not work at others. So, we kept thinking it was okay right until 2 hours before the deadline. Overall, we got back to what our original project was, but we were not able to create a good devpost or video submission for the online hackathon. Overall, this hackathon taught me about being more decisive in time management. I realize now we should have stopped working on our problem, and reverted to a previous submission well before the time of submission. Maybe my experience can teach some of you lessons when you ever go to a hackathon. hat stopped the installation of the Oculus.</p>
        <p>For the complete submission of our project, visit our <a href="https://devpost.com/software/discoursevr">devpost</a>. For the source code, visit our <a href="https://github.com/Breality/DiscourseVR">github repository</a>.</p>
      </v-col>
    </v-row>
    <v-row justify="center" align="center" class="grey darken-4 pt-10 ma-0 pb-0">
      <v-col cols="12" class="pa-0">
      </v-col>
      
    </v-row>
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