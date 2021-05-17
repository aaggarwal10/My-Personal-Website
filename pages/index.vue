<template>
  <v-app dark>
    <meta property='og:image' content='/blog-imgs/logo-aa.png'/>
    <v-app-bar fixed app dense :color = appNavColor :absolute = appNavPos> <!--black / remove abs -->
        <v-tabs centered color="white" hide-slider show-arrows>
            <v-tabs-slider></v-tabs-slider>
            <v-tab :ripple="true" @click="$vuetify.goTo('#home')">Home</v-tab>
            <v-tab :ripple="true" @click="$vuetify.goTo('#about')">About</v-tab>
            <v-tab :ripple="true" @click="$vuetify.goTo('#skills')">Skills</v-tab>
            <v-tab :ripple="true" @click="$vuetify.goTo('#projects')">Projects</v-tab>
            <v-tab :ripple="true" @click="$vuetify.goTo('#awards')">Awards</v-tab>
            <v-tab :ripple="true" @click="$vuetify.goTo('#experiences')">Experiences</v-tab>
            <v-tab :ripple="true" @click="$vuetify.goTo('#contact')">Contact</v-tab>
            <v-tab :ripple="true" href="/blog">Blog</v-tab>
            <v-tab :ripple="true" target="blank" href="/Anish_Aggarwal_Resume.pdf">Resume</v-tab>
          
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
              <h1 class = "pb-2 display-3 font-weight-medium">
                Anish Aggarwal
              </h1>
              <h3 class = "display-1 font-weight-regular">
                Computer Science, UWaterloo '25 | Schulich Leader '20
              </h3>
            </v-col>
          </v-row>
        </v-overlay>
    </v-img>
    
    <v-row justify="center" class="pa-0 white">
      <v-col cols="12" class = "mt-16">
        <h2 class="display-3 font-weight-bold black--text mt-2 mb-6" id="about" align="center">About Me</h2>
      </v-col>
    </v-row>

    <v-row justify="center" vertical-align="center" class="white pb-16">
      <v-col sm="8" xs="8" md="4" lg = "4" class>
        <v-container fill-height fluid class="profile"> 
          <v-img eager contain align="center" justify = "center" src = "/profile2.jpg"></v-img>
        </v-container>
      </v-col>
      <v-col sm="8" xs="8" md="4" lg = "4">
          <v-card color="white" elevation=0>
            <v-card-text left>
              <h2 class="font-weight-regular black--text mt-10">
                Hi, I'm Anish. Currently, I am a Computer Science student at the University of Waterloo with a passion for Virtual Reality and Machine Learning.
                <br>
                <br>
                <br>
                I like teaching as I firmly believe that teaching helps solidify what I have learned.
                <br>
                <br>
                <div class = "quote font-weight-light"> The best way to learn is to teach <br> - Julius Oppenheimer </div>
                <br>
                <br>
                I am currently working on Reinforcement Learning AI applications with projects being uploaded to my youtube channel: AACodes.
              </h2>
            </v-card-text>
          </v-card>
      </v-col>
    </v-row>

    <v-row id="skills">
     <v-col cols="12" class="py-0">
       <v-parallax src="/caypt.jpg" height="300">
        <v-overlay absolute black opacity = "0.6">
         <h2 class="display-3 font-weight-bold white--text text-center mb-8" id="about" >Skills</h2>
         <v-chip-group justify="center" align="center">
         <v-chip v-for="(skill,index) in skills" :key="index" class="ma-2">{{skill.name}} </v-chip>
         </v-chip-group>
        </v-overlay>
       </v-parallax>
     </v-col>
   </v-row>

   <v-row justify="center" align="center" class="white pt-16 pb-0">
      <v-col cols="12" class="pb-0">
        <h2 class="display-3 font-weight-bold black--text mt-2 mb-6" id="projects" align="center">Projects</h2>
      </v-col>
    </v-row>
    <v-app class="white" >
      <v-row justify="center" align="center" class = "d-flex flex-wrap align-content-space-around white pt-5 pl-5 pr-5 pb-16 mb-16 ma-0">
          <v-hover v-slot="{hover}" v-for="(project,index) in projects" :key="index">
            <v-col xs="10" sm="5" md = "4" lg="4">
              <v-card flat min-width="225" target="blank" :href = "project.ref">
                <v-img :src="project.imgsrc" eager height="400">
                  <v-expand-transition>
                    <v-overlay v-if="hover" absolute color="blue darken-4" opacity="0.8">
                      <v-card-text  align="center" class="white--text body-1">
                        {{project.description}}
                      </v-card-text>
                    </v-overlay >
                </v-expand-transition>
              </v-img>
                <v-card-title class = "font-weight-bold title">{{project.name}}</v-card-title>
              </v-card>
            </v-col>
            </v-hover> 
      </v-row>
    </v-app>

    <v-row justify="center" align="center" id="awards" class = "mt-0">
     <v-col cols="12" class="py-0 mt-0">
       <v-parallax src="/sciolymp.jpg" height="300">
        <v-overlay absolute black opacity = "0.6" align="center">
         <h2 class="display-3 font-weight-bold white--text text-center mb-8" id="about">Awards</h2>
         <v-chip v-for="(award,index) in awards" :key="index" class="ma-2" target = "blank" :href = award.ref>{{award.name}} </v-chip>
        </v-overlay>
       </v-parallax>
     </v-col>
   </v-row>

   <v-row justify="center" align="center" class="white pt-16 pb-0">
      <v-col cols="12" class="pb-0">
        <h2 class="display-3 font-weight-bold black--text mt-2 mb-6" id="experiences" align="center">Experiences</h2>
      </v-col>
    </v-row>
    <v-app class="white" >
      <v-row justify="center" align="center" class = "d-flex flex-wrap align-content-space-around white pt-5 pl-5 pr-5 pb-16 mb-16 ma-0">
          <v-hover v-slot="{hover}" v-for="(exp,index) in experiences" :key="index">
            <v-col xs="10" sm="5" md = "4" lg="4">
              <v-card flat min-width="225" target="blank" :href = "exp.ref">
                <v-img :src="exp.imgsrc" eager height="400">
                  <v-expand-transition>
                    <v-overlay v-if="hover" absolute color="blue darken-4" opacity="0.8">
                      <v-card-text  align="center" class="white--text body-1">
                        {{exp.description}}
                      </v-card-text>
                    </v-overlay >
                </v-expand-transition>
              </v-img>
                <v-card-title class = "font-weight-bold title">{{exp.name}}</v-card-title>
                <v-card-subtitle class = "font-weight-bold title">{{exp.role}}</v-card-subtitle>
              </v-card>
            </v-col>
            </v-hover> 
      </v-row>
    </v-app>
  
    <v-row justify="center" align="center" id="contact" class = "mt-0">
     <v-col cols="12" class="py-0 mt-0">
       <v-parallax src="/skating.jpg" height="600">
        <v-overlay absolute black opacity = "0.6" align = "left" class = "pt-16">
         <h2 class="display-3 font-weight-bold white--text text-center mb-8 pt-0" id="about">Contact Me</h2>
         <pre><code v-highlight class="python caption pa-3" color="black">import json
anish_data = {
  "name": "Anish Aggarwal",
  "age": 18,
  "from": "Windsor, Ontario",
  "occupation": "Computer Science Student",
  "location": "University of Waterloo",
  "contact-links": {
    "email": "<a href="mailto:hello@anishaggarwal.ca" class="link">hello@anishaggarwal.ca</a>",
    "github": "<a href="https://github.com/aaggarwal10" class="link">https://github.com/aaggarwal10</a>",
    "linkedin": "<a href="https://www.linkedin.com/in/aaggarwal10/" class="link">https://www.linkedin.com/in/aaggarwal10/</a>",
    "devpost": "<a href="https://devpost.com/aaggarwal10" class="link">https://devpost.com/aaggarwal10</a>"
  }
} 
f_out = open("anish_data-{{ new Date().getMonth() + 1 }}/{{ new Date().getDate() }}/{{ new Date().getFullYear() }}.json", 'w')
json.dump(anish_data, f_out)
f_out.close()</code></pre>
        </v-overlay>
       </v-parallax>
     </v-col>
   </v-row>

  <v-container class="pa-11"></v-container>
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
    }, // https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API
    skills: [
        {name: "Artificial Intelligence"},
        {name: "C++"},
        {name: "C"},
        {name: "C#"},
        {name: "Unity"},
        {name: "Python"},
        {name: "Vue.js"},
        {name: "Virtual Reality"},
        {name: "Augmented Reality"},
      ],  
    projects: [
        {name: "Discourse VR", description: "A debate analyser that allows for directed feed back and recordings of parliamentary debates.", imgsrc: "/projects/discourse.jpg", ref: "https://devpost.com/software/discoursevr"},
        {name: "ChatSpace VR", description: "WinHacks 2021 Winner! A virtual space that allows users to play table activities, go on campus walks, and voice chat.", imgsrc: "/projects/chatspace.jpg", ref: "https://devpost.com/software/chatspace-vr"},
        {name: "Perfect Snake AI", description:"Using Graph Theory and a Hamiltonian Cycle Generator to make the perfect snake game on odd grids.", imgsrc: "/projects/smartsnake.gif", ref:"https://github.com/aaggarwal10/Artificial-Intelligence/tree/main/Classic%20Snake%20AI/Hamiltonian%20Method"},
        {name: "Open World VR App", description: "Using Unity, Windows Mixed Reality Headset, and a Xbox 360 Kinect to put players into an Open World VR game.", imgsrc: "/projects/vropenworld.gif", ref:"https://github.com/Breality/ICS4U-FSEV2"},
        {name: "VR Home Modeling", description:"Using voice activated commands, you can (virtually) place furniture items in your house. When you like what you see, you can get the retail prices of your items.", imgsrc: "/projects/vrhouse.png", ref: "https://github.com/Breality/virtualhousemodelling"},
        {name: "EyeGuide", description:"EyeGuide is a utility belt that will aid you when you can't see, and connect you to help when you need it.", imgsrc: "/projects/eyeguide.jpg", ref: "https://devpost.com/software/eyeguide#updates"},
        {name: "AR-itus", description:"Rehabilitating individuals who are suffering with hand-eye coordination problems with the use of Augmented Reality technology.", imgsrc: "/projects/aritus.png", ref:"https://github.com/RealityVirtually2019/AR-itus"},
        {name: "Teleclinic", description: "Online medical clinic that helps make your apppointments and walk-ins seamless.", imgsrc: "/projects/teleclinic.jpg", ref: "https://github.com/aaggarwal10/Teleclinic"}
      ],
    awards: [
      {name: "Schulich Leader 2020", ref: "https://www.schulichleaders.com/scholars#slide-scholars"},
      {name: "Governor General Award", ref: "https://www.gg.ca/en/honours/recipients/116-105361"},
      {name: "Des Cartes UWaterloo National Scholarship", ref: undefined}
    ],
    experiences: [
        {name: "MIT Media Club", role: "Participant", description:"Spent 5 days in the Reality Virtually Hackathon at MIT Media Lab learning the latest skills in AR/VR Development.", imgsrc: "/experiences/realityvr.png", ref:"https://www.uwindsor.ca/science/418/science-olympiad"},
        {name: "CodeReach", role: "Director & Senior Teacher", description:"CodeReach helps young students learn the basics of computer science and programming to prepare them for success in STEM. I managed the CodeReach teachers and staff. I also taught a class of students myself.", imgsrc: "/experiences/codereach.png", ref:"https://codereach.ca"},
        {name: "CaYPT", role:"Team Captain", description: "I lead my team to a 3rd place finish at a National Physics Competition. We had to solve 10 open-ended physics problems with experiments.", imgsrc: "/experiences/caypt-logo.png", ref:"https://stemfellowship.org/competitions/caypt/"},
        {name: "MasseyHacks V", role: "Logistics Exec", description:"Organized and helped manage Canada's largest high school hackathon.", imgsrc: "/experiences/masseyhacks.png", ref: "https://masseyhacks.ca/"},
        {name: "Massey CS Club", role: "Senior Leader", description:"Taught algorithmic design to senior high school students and prepared them for computing contests.", imgsrc: "/experiences/csclub.png", ref: "https://vmcs.club/"},
        {name: "Massey Science Team", role: "Leader", description:"Taught high school students the beauty of different sciences preparing them to compete at the Science Olympic competitions.", imgsrc: "/experiences/sciolympics.jpg", ref: "https://www.uwindsor.ca/science/418/science-olympiad"}
      ],
    icons: [
        {type: 'mdi-facebook', link: 'https://www.facebook.com/aaggarwal10'},
        {type: 'mdi-linkedin', link: 'https://www.linkedin.com/in/aaggarwal10/'},
        {type: 'mdi-instagram', link: 'https://www.instagram.com/anish_a10/'},
        {type: 'mdi-github', link: 'https://github.com/aaggarwal10'},
        {type: 'mdi-email', link: "mailto:hello@anishaggarwal.ca"}
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
      }
 
      if (direction === this.$waypointMap.DIRECTION_TOP) {
        if ((!this.navBarMode) && (this.curCount == this.changeCount)){
          this.appNavColor = "black"
          this.appNavPos = false
        } else if (this.navBarMode){
          this.navBarMode = false
          this.curCount = 1
        } else{
          this.curCount += 1
        }
      }
    }
  }
}
</script>

<style scoped>

.profile:hover {
  transform: scale(1.01); /* (150% zoom - Note: if the zoom is too large, it will go outside of the viewport) */
}
.quote{
  text-align: right;
  font-style: italic;
}
.contact-title{
  color: #9473a5;
  font-family: Consolas,monaco,monospace; 
}
.contact-colon{
  color: #ff7f50;
  font-weight: bold;
}
.contact-str{
  color: #3a7b3a;
  font-family: Consolas,monaco,monospace;
}
.contact-int{
  color: #4287f5;

}
a.link{
  text-decoration: underline;
  text-decoration-color: #ec7600;
}
a.link:hover{
  text-decoration: none;
}
.v-application code {
    background-color: rgb(32, 29, 29);
}
</style>