<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-secondary" elevated>
      <q-toolbar >
        <q-toolbar-title>
          CAR ESTOQUE
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>

export default {
  name: 'MainLayout',

  data () {

  }
}
</script>
