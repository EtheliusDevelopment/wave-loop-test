<template>
 <div v-for="(product, index) in dbProducts" :key="index">
    <Single
      :product="product"
      :products="dbProducts"
      @addProductToCompare="ChangeT($event)"
      @removeProductToCompare="ChangeD($event)"
      @like-it="addToLikes($event)"
      @dislike-it="removeFromLikes($event)"
    />
  </div>
  <BottomBar
  :productsToCompare="lsCompare"
  />

  <div class="q-pa-lg flex flex-center">
    <q-pagination
      v-model="current"
      :max="3"
      direction-links
      icon-prev="fast_rewind"
      icon-next="fast_forward"
    />
  </div>
</template>

<script>
import data from "../../db_products/db.json";
import Single from "./Single.vue";
import { ref } from "vue";
import BottomBar from './BottomBar.vue'
export default {
  components: {
    Single,
    BottomBar
  },
  methods: {
    ChangeT(product) {
      this.lsCompare = [...this.lsCompare, product];

    },
    ChangeD(product) {
      this.lsCompare = this.lsCompare.filter((prdc)=>{
          return prdc.id != product.id
      })

    },
    addToLikes(product) {
     this.lsLike = [...this.lsLike, product];
     localStorage.setItem('productsLike', JSON.stringify(this.lsLike))


    },
    removeFromLikes(product) {
      this.lsLike = this.lsLike.filter((prdc)=>{
          return prdc.id != product.id
      })
      localStorage.setItem('productsLike', JSON.stringify(this.lsLike))

    },
  },
  setup() {
    const dbProducts = data;
    let lsCompare = ref([]);
    let lsLike = ref([]);
    const getProduct = (product) => {
      alert("product");
    };


    return {
      dbProducts,
      Single,
      lsCompare,
      getProduct,
      BottomBar,
      lsLike,
      current: ref(1)
    };
  },
};
</script>

<style lang="scss" scoped>

</style>
