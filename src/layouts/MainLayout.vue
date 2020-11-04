<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-primary">
        <q-btn
          v-if="$route.path != '/'"
          flat
          dense
          round
          icon="arrow_back"
          aria-label="Back button"
          @click="$router.go(-1)"
        />

        <q-toolbar-title> Countries </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: "MainLayout",
  data() {
    return {}
  },
}
</script>
