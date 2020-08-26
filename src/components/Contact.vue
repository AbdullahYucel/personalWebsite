<template>
  <v-list-item>
    <v-list-item-icon class="pa-0 mr-2">
      <v-btn icon>
        <a :href="contact.link" target="_blank">
          <v-icon :style="contact.style">{{contact.icon}}</v-icon>
        </a>
      </v-btn>
    </v-list-item-icon>
    <v-list-item-content>
      <v-list-item-title>{{contact.value}}</v-list-item-title>
      <v-list-item-subtitle>{{contact.name}}</v-list-item-subtitle>
    </v-list-item-content>
  </v-list-item>
</template>

<script>
export default {
  props: {
    contact: Object,
    default: function () {
      return {};
    },
  },
};
</script>

<style>
</style>