<template>
  <v-dialog v-model="visible" persistent max-width="400">
    <v-card>
      <v-card-title class="headline">Terminé</v-card-title>
      <v-card-text>
        Le PDF avec la brochure est prêt. Vous pouvez le télécharger depuis
        we-transfert en cliquant sur le bouton ci-dessous.
        <div class="text-xs-center">
          <v-btn color="success" :href="url" target="_blank">Télécharger</v-btn>
        </div>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="red darken-1" flat @click="$emit('close', true)"
          >Fermer</v-btn
        >
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    visible: Boolean,
    url: {
      type: String,
      default: ''
    }
  }
}
</script>
