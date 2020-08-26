<template>
  <v-card flat color="transparent" max-width="350px">
    <v-card-title>
      <v-layout>
        <v-flex>
          <v-card
            color="#dee2e6"
            width="100px"
            height="100px"
            elevation="15"
            style="border-radius:22px"
          >
            <a :href="app.link" target="_blank">
              <v-img :src="logo(app.logo)" style="top:1px"></v-img>
            </a>
          </v-card>
        </v-flex>
        <v-flex xs12 sm6 md12 class="ml-5 px-0">
          <div class>
            <a :href="app.link" target="_blank">{{app.name}}</a>
          </div>
          <div>
            <v-chip pill color="blue" dark>{{app.price}}</v-chip>
          </div>
          <template v-for="(platform,i) in app.platforms">
            <v-btn icon :key="i">
              <v-icon>{{platform.icon}}</v-icon>
            </v-btn>
          </template>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <div>{{app.description}}</div>
      <div class="title mt-2">Used Technologies</div>
      <v-layout>
        <template v-for="(tech,i) in app.technologies">
          <v-flex :key="i" xs2 class="d-flex align-center justify-center flex-column mx-1">
            <v-btn icon>
              <v-icon :style="tech.style">{{tech.icon}}</v-icon>
            </v-btn>
            <div class="caption">{{tech.name}}</div>
          </v-flex>
        </template>
      </v-layout>
      <div class="title mt-2">Code</div>
      <div>
        <a :href="app.code.link" target="_blank">
          <v-btn icon>
            <v-icon :style="app.code.style">{{app.code.icon}}</v-icon>
          </v-btn>
        </a>
      </div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    app: {
      type: Object,
      default: function () {
        return {};
      },
    },
  },
  methods: {
    logo(name) {
      return require("../assets/" + name);
    },
  },
};
</script>

<style>
</style>