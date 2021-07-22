<template>

 <div v-if="productsToCompare.length>0" class="bottom-bar">
   <h5 class="text-bar text-white" v-if="productsToCompare.length<3">seleziona altri {{3 -productsToCompare.length }} prodotti per confrontarli</h5>
   <h5 class="text-bar text-white" v-else>Ora puoi comparare i prezzi</h5>
   <q-btn outline style="color: white;" label="Confronta" class="button" @click="openModal()" :disable="productsToCompare.length<3"/>
 </div>
 <q-dialog v-model="toolbar">
      <q-card>
        <q-toolbar>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo.svg">
          </q-avatar>


          <q-btn flat round dense icon="close" v-close-popup />
        </q-toolbar>

        <q-card-section>
            <h5>grazie per comparare con noi</h5>
        </q-card-section>
      </q-card>
    </q-dialog>
</template>

<script>
import { ref } from 'vue'

 export default {

   props: {
    list: {
      type: Array
    },
    productsToCompare: {
      type: Array
    }
   },
   setup() {

     const toolbar = ref(false)

     return {
        openModal() {
          this.toolbar = !this.toolbar
        },
        toolbar,
     }
   },

 }
</script>

<style lang="scss" scoped>
  .bottom-bar{
    width: 100%;
    height: 50px;
    background-color: $accent;
    position:fixed;
    bottom: 0;
    left: 0;
    z-index: 999999;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 5vw;
    opacity: .9;

  }

  .button {
    height: 4vh;
    border-radius: 50px;
    opacity: .4;

  }

  .text-bar{
    font-family: Avenir-Book;
    font-size: 20px;
    opacity: .4;
  }
</style>

