<template>
  <q-page class="q-pb-xl">
    <div class="row" v-if="$q.platform.is.desktop">
      <!-- Component will be rendered if viewed on a desktop -->
      <card-view
        class="col-3 q-pa-md"
        v-for="(country, index) in countries"
        :key="index"
        :data="country"
      />
    </div>
    <q-list separator v-else>
      <!-- Component will be rendered if viewed on a mobile -->
      <list-view
        v-for="(country, index) in countries"
        :key="index"
        :data="country"
      />
    </q-list>
    <q-page-sticky position="bottom-right" :offset="[18, 18]">
      <!-- Component containing buttons to download excel, csv and xml files -->
      <q-fab color="primary" icon="keyboard_arrow_up" direction="up">
        <q-fab-action
          color="primary"
          @click="exportToExl('xml')"
          icon="fas fa-file-code"
        />
        <q-fab-action
          color="primary"
          @click="exportToExl('csv')"
          icon="fas fa-file-csv"
        />
        <q-fab-action
          color="primary"
          @click="exportToExl('xls')"
          icon="fas fa-file-excel"
        />
      </q-fab>
    </q-page-sticky>
  </q-page>
</template>

<script>
import axios from "axios"
import exportFromJSON from "export-from-json"
import ListView from "components/ListView.vue"
import CardView from "components/CardView.vue"
export default {
  name: "PageIndex",
  data() {
    return {
      countries: [],
    }
  },
  components: { ListView, CardView },
  methods: {
    getData() {
      // func to get datas from api
      // api url
      const url = "https://restcountries.eu/rest/v2/all"
      // consume api with axios
      axios
        .get(url)
        .then((response) => {
          this.countries = response.data
        })
        .catch((error) => {
          console.log(error)
        })
    },

    exportToExl(type) {
      // function to convert JSON data to another datas types like xls, csv and xml.
      const data = this.countries
      const fileName = "Countries"
      const exportType = type
      // exportFromJSON lib help us to convert file
      exportFromJSON({ data, fileName, exportType })
    },
  },
  mounted() {
    // After the component mounted, it will execute the function that fetch the datas from the api.
    this.getData()
  },
}
</script>
