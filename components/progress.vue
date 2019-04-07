<template>
  <v-dialog v-model="visible" hide-overlay persistent width="300">
    <v-card color="primary">
      <v-card-text
        >Un instant... Je génère le PDF
        <v-progress-linear
          indeterminate
          color="white"
          class="mb-0"
        ></v-progress-linear>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    visible: Boolean
  }
}
</script>
