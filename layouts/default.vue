<template>
  <v-app dark>
    <v-toolbar fixed app>
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer app>
      <span>&nbsp;&copy; 2019 Jacques Supcik</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: 'Passeport vacances Fribourg 2019 - Commande de brochure'
    }
  }
}
</script>
