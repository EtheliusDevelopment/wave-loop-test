<template>
  <q-layout view="lHh Lpr lFf">
    <q-header> </q-header>

    <q-drawer show-if-above bordered class="drawer">
      <Drawerutils />

    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>


import { defineComponent, ref } from "vue";
import Drawerutils from '../components/drawer-components/Drawer-utils.vue'

export default defineComponent({
  name: "MainLayout",
  components: {
    Drawerutils
  },
  setup () {

    return {
      Drawerutils,
    }
  }

  });
</script>

<style lang="scss">
aside.q-drawer {
    // margin-top: 15vh;
    // margin-bottom: 5vh;
    width: 20vw !important;
    position: absolute   !important;
}
</style>
