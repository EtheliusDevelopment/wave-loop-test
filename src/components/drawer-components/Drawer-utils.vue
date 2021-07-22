<template>

  <q-list>
    <q-item-label> </q-item-label>
  </q-list>
  <Alimentazione/>
  <Categorie />
  <Marche/>
  <Potenza />
  <Recensioni/>
  <Scegli />
  <Tipologia />
  <Utilizzo />
</template>

<script>
import Alimentazione from './Alimentazione.vue'
import Categorie from './Categorie.vue'
import Marche from './Marche.vue'
import Potenza from './Potenza.vue'
import Recensioni from './Recensioni.vue'
import Scegli from './Scegli.vue'
import Tipologia from './Tipologia.vue'
import Utilizzo from './Utilizzo.vue'
export default {

  components: {
      Alimentazione,
      Categorie,
      Marche,
      Potenza,
      Recensioni,
      Scegli,
      Tipologia,
      Utilizzo
  },
  setup() {

    return {


    }
  },
}
</script>
