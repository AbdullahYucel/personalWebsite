<template>
  <v-container id="mainContent">
    <!-- ABOUT STARTS -->
    <v-layout wrap>
      <v-flex>
        <div class="baslik">ABOUT ME</div>
      </v-flex>

      <v-flex>
        <div class="row">
          <v-flex
            class="paragraf column"
            xs12
            sm6
          >I graduated from Ege University as an education technologies teacher. Then, I was forced to change career by 3rd party reasons. Now, I'm a junior front end developer by using those technologies.</v-flex>
          <v-flex class="paragraf column" style="border-left:2px solid;" xs12 sm6>
            <v-layout wrap>
              <template v-for="(talent,i) in knowledge">
                <div
                  :key="i"
                  class="px-10 d-flex align-center justify-center flex-column"
                  style="max-width:100px;"
                >
                  <h4>{{talent.name}}</h4>
                  <v-btn icon>
                    <v-icon :style="talent.style">{{talent.icon}}</v-icon>
                  </v-btn>
                </div>
              </template>
            </v-layout>
          </v-flex>
        </div>
        <v-divider dark color="black"></v-divider>
        <v-flex
          class="paragraf row mb-5"
        >I'm still trying to improve my back-end and database/query technologies skills like GraphQL, MongoDB and NodeJS with taking courses and making sample projects.</v-flex>
        <v-divider dark color="black"></v-divider>
        <v-flex class="paragraf row">{{aboutText}}</v-flex>
      </v-flex>
    </v-layout>
    <!-- ABOUT FINISH -->
    <!-- PORTFOLIO STARTS -->
    <v-layout id="portfolio" wrap my-5>
      <v-flex xs12>
        <div class="baslik">PORTFOLIO</div>
      </v-flex>
      <v-flex xs12 class="mt-5">
        <v-layout wrap>
          <template v-for="(app, i) in apps">
            <v-flex :key="i" xs12 sm6 md4>
              <Portfolio :app="app" />
            </v-flex>
          </template>
        </v-layout>
      </v-flex>
    </v-layout>
    <!-- PORTFOLIO FINISHES -->
    <!-- CONTACT START -->
    <v-layout wrap>
      <v-flex xs12>
        <div class="baslik">CONTACT</div>
      </v-flex>

      <template v-for="(contact,i) in contactLinks">
        <v-flex xs12 sm4 :key="i" class="contact-margin">
          <Contact :contact="contact" />
        </v-flex>
      </template>
    </v-layout>
    <!-- CONTACT FINISHES -->
  </v-container>
</template>

<script>
import Portfolio from "@/components/Portfolio.vue";
import Contact from "@/components/Contact.vue";
export default {
  components: {
    Portfolio,
    Contact,
  },
  data() {
    return {
      aboutText:
        "This website is designed for present me and my skills. By the way, I hope to attract attention of employers and companies.",
      apps: [
        {
          name: "Ege Eğitim 360",
          logo: "360.png",
          link: "https://ege360.abdullahyucel.com",
          description:
            "360° Virtual Tour of Ege University, Faculty of Education",
          price: "Open Source",
          platforms: [
            {
              name: "web",
              icon: "mdi-web",
            },
            {
              name: "open-source",
              icon: "mdi-open-source-initiative",
            },
          ],

          technologies: [
            {
              name: "Vue",
              icon: "mdi-vuejs",
              style: {
                background: "",
                color: "#41B883",
                maxWidth: "50px",
              },
            },
            {
              name: "Bootstrap",
              icon: "mdi-bootstrap",
              style: {
                background: "",
                color: "#602C50",
                maxWidth: "50px",
              },
            },
            {
              name: "JSon",
              icon: "mdi-code-json",
              style: {
                background: "",
                color: "#17559D",
                maxWidth: "50px",
              },
            },
          ],
          code: {
            name: "GitHub",
            icon: "mdi-github",
            link: "https://github.com/AbdullahYucel/Ege360",
            style: {
              background: "",
              color: "#211F1F",
              maxWidth: "50px",
            },
          },
        },
        {
          name: "E-Commerce",
          description: "Shoe selling  website",
          price: "Open Source",
          logo: "ticaret.png",
          link: "https://fakestore.abdullahyucel.com",

          platforms: [
            {
              name: "web",
              icon: "mdi-web",
            },
            {
              name: "open-source",
              icon: "mdi-open-source-initiative",
            },
          ],

          technologies: [
            {
              name: "Javascript",
              icon: "mdi-language-javascript",
              style: {
                background: "#323330",
                color: "#F0DB4F",
                maxWidth: "50px",
              },
            },
            {
              name: "JSon",
              icon: "mdi-code-json",
              style: {
                background: "",
                color: "#17559D",
                maxWidth: "50px",
              },
            },
          ],
          code: {
            name: "GitHub",
            icon: "mdi-github",
            link: "https://github.com/AbdullahYucel/Fake-Store",
            style: {
              backgroundColor: "",
              color: "#211F1F",
              maxWidth: "50px",
            },
          },
        },
        {
          name: "Personal Website",
          description: "My own website",
          price: "Open Source",
          logo: "vesika3.png",
          link: "https://www.abdullahyucel.com",
          platforms: [
            {
              name: "web",
              icon: "mdi-web",
            },
            {
              name: "open-source",
              icon: "mdi-open-source-initiative",
            },
          ],

          technologies: [
            {
              name: "Vue",
              icon: "mdi-vuejs",
              style: {
                background: "",
                color: "#41B883",
                maxWidth: "50px",
              },
            },
            {
              name: "Bootstrap",
              icon: "mdi-bootstrap",
              style: {
                background: "",
                color: "#602C50",
                maxWidth: "50px",
              },
            },
            {
              name: "Vuetify",
              icon: "mdi-vuetify",
              style: {
                background: "",
                color: "#3482CF",
                maxWidth: "50px",
              },
            },
          ],
          code: {
            name: "GitHub",
            icon: "mdi-github",
            link: "https://github.com/AbdullahYucel/personalWebsite",
            style: {
              backgroundColor: "",
              color: "#211F1F",
              maxWidth: "50px",
            },
          },
        },
      ],
      contactLinks: [
        {
          name: "Email",
          value: "Abdullahyucel@outlook.com.tr",
          icon: "mdi-email-outline",
          link: "mailto:Abdullahyucel@outlook.com.tr",
          style: {
            color: "#B23121",
            maxWidth: "50px",
          },
        },
        {
          name: "LinkedIn",
          value: "Abdullah YÜCEL",
          icon: "mdi-linkedin",
          link: "https://www.linkedin.com/in/abdullah-yucel",
          style: {
            color: "#2867B2",
            maxWidth: "50px",
          },
        },
        {
          name: "GitHub",
          value: "AbdullahYucel",
          icon: "mdi-github",
          link: "https://www.github.com/AbdullahYucel",
        },
      ],
      knowledge: [
        {
          name: "Javascript",
          icon: "mdi-language-javascript",
          style: {
            background: "#323330",
            color: "#F0DB4F",
            maxWidth: "50px",
          },
        },
        {
          name: "Vue",
          icon: "mdi-vuejs",
          style: {
            background: "",
            color: "#41B883",
            maxWidth: "50px",
          },
        },
        {
          name: "React",
          icon: "mdi-react",
          style: {
            background: "",
            color: "#61DBFB",
            maxWidth: "50px",
          },
        },
        {
          name: "GraphQL",
          icon: "mdi-graphql",
          style: {
            background: "",
            color: "#e535ab",
            maxWidth: "50px",
          },
        },
        {
          name: "MongoDB",
          icon: "mdi-database-marker",
          style: {
            background: "#E8E7D5",
            color: "#570000",
            maxWidth: "50px",
          },
        },
        {
          name: "NodeJS",
          icon: "mdi-nodejs",
          style: {
            background: "",
            color: "#08a045",
            maxWidth: "50px",
          },
        },
        {
          name: "Bootstrap",
          icon: "mdi-bootstrap",
          style: {
            background: "",
            color: "#602C50",
            maxWidth: "50px",
          },
        },
      ],
    };
  },
};
</script>

<style>
</style>