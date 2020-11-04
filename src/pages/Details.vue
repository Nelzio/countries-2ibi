<template>
  <q-page class="q-pb-xl">
    <div>
      <desktop :data="data" v-if="$q.platform.is.desktop" />
      <mobile :data="data" v-else />
    </div>
  </q-page>
</template>

<script>
import axios from "axios"
import Mobile from "components/details/Mobile.vue"
import Desktop from "components/details/Desktop.vue"
export default {
  data() {
    return {
      data: {},
    }
  },
  components: { Mobile, Desktop },
  methods: {
    getData() {
      // func to get datas from api
      const url =
        "https://restcountries.eu/rest/v2/alpha/" + this.$route.params.codeParam
      axios
        .get(url)
        .then((response) => {
          this.data = response.data
        })
        .catch((error) => {
          console.log(error)
        })
    },
  },
  mounted() {
    // After the component mounted, it will execute the function that fetch the datas from the api.
    this.getData()
  },
}
</script>

<style>
</style>