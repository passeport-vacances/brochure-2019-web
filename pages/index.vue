<template>
  <v-layout>
    <v-flex text-xs-center>
      <v-btn
        class="primary"
        :disabled="loading || done"
        :loading="loading"
        @click="test"
        >Bons-à-tirer</v-btn
      >

      <Progress :visible="loading" />
      <DownloadBox :visible="done" :url="we_url" @close="done = false" />
    </v-flex>
  </v-layout>
</template>

<script>
import Progress from '~/components/progress.vue'
import DownloadBox from '~/components/download_box.vue'

export default {
  components: {
    Progress,
    DownloadBox
  },
  data() {
    return {
      we_url: undefined,
      loading: false,
      done: false
    }
  },
  methods: {
    test(event) {
      this.loading = true
      this.$axios
        .$get('https://pvfr19-brochure.app.supcik.net/bons-a-tirer')
        .then(result => {
          this.loading = false
          this.done = true
          if (result.success) {
            this.we_url = result.url
          } else {
            this.we_url = undefined
          }
        })
    }
  }
}
</script>
