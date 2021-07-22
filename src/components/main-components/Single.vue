<template>
  <!-- <h2 class="text-teal">{{product.brand}}</h2>
    <h2 class="text-orange">{{product.description}}</h2>
    <h2 class="text-blu">PRICE {{product.price}}</h2>
    <img src="~assets\img-test.png" alt="" width="100" height="100">
    <h2 class="text-green">DISCOUNTED PRICE {{product.discountedPrice}}</h2>
    <h2>{{product.specialOffer}}</h2>
    <h2 class="text-red">{{product.like}}</h2> -->
  <q-card class="my-card q-ml-xl q-mb-xl">
    <img src="~assets\caldaia.png" class="img-product" />

    <q-card-section>
      <h5 v-if="product.specialOffer" class="ribon">Risparmi il 20%</h5>
      <h4 class="title-card">{{ product.brand }}</h4>
      <p class="description-card">{{ product.description }}</p>
      <h3 v-if="!product.specialOffer" class="main-price text-primary">
        {{ product.price }}
      </h3>
      <div v-if="product.specialOffer" class="price-combo">
        <h3 class="discounted-price text-secondary">
          {{ product.discountedPrice }}
        </h3>
        <h5 class="first-price text-black">{{ product.price }}</h5>
      </div>

      <p class="fixed-descr text-secondary">
        Sopralluogo ed instalazione inclusi
      </p>
      <img
        :class="{ liked: heartState }"
        class="img-card"
        src="~assets\heart.svg"
        alt="heart-like"
        width="30"
        @click="preferFunct(product)"
      />

      <div class="reviews">
        <div class="stars">
          <q-icon class="icon-star" name="star_rate" color="primary" />
          <q-icon class="icon-star" name="star_rate" color="primary" />
          <q-icon class="icon-star" name="star_rate" color="primary" />
          <q-icon class="icon-star" name="star_rate" color="primary" />
          <q-icon class="icon-star" name="star_border" color="primary" />
        </div>

        <q-checkbox
          id="checkbox"
          v-model="val"
          @click="passEvent(product)"
          label="CONFRONTA"
        />
      </div>
    </q-card-section>
  </q-card>
</template>

<script>
import { ref } from "vue";

export default {
  props: {
    product: {
      type: Object,
      required: true,
    },
    products: {
      type: Array,
      required: true,
    },
  },
  methods: {
    passEvent(product) {
      if (this.val == true) {
        this.$emit("addProductToCompare", product);
      } else {
        this.$emit("removeProductToCompare", product);
      }
    },
    preferFunct(product) {
      this.heartState = !this.heartState;
      if (this.heartState == true) {
        this.$emit("like-it", product);
      } else {
        this.$emit("dislike-it", product);
      }
    },
  },
  setup(props, context) {
    const heartState = ref(false);
    const val = ref(false);
    let lsCompare = ref([]);

    const confrontaFunct = () => {
      // alert(JSON.stringify(props.products));
      val.value ? context.emit("filterProduct", props.product) : alert("hala");
    };

    return {
      heartState,
      val,
      confrontaFunct,
      lsCompare,
    };
  },
};
</script>

<style lang="scss" scoped>
.my-card {
  width: 100%;
  max-width: 20vw;
}

.img-card {
  cursor: pointer;
  filter: invert(0%) sepia(13%) saturate(7492%) hue-rotate(36deg)
    brightness(88%) contrast(95%);
  opacity: 0.2;
  transition: all 0.2s ease-in;
  position: absolute;
  bottom: 45vh;
  left: 17vw;
}

.liked {
  filter: invert(0%) sepia(13%) saturate(7492%) hue-rotate(36deg)
    brightness(88%) contrast(95%);
  opacity: 1;
}

.title-card {
  font-size: 12px;
  font-weight: 700;
  text-transform: uppercase;
  color: #000000;
  margin-bottom: 0;
  line-height: 2vh;
}

.description-card {
  font-size: 15px;
  margin-bottom: 0;
}
.fixed-descr {
  font-size: 12px;
  font-weight: 700;
  margin: 0;
  padding-bottom: 0.8vh;
  border-bottom: 1px solid #00000042;
}
#checkbox {
  opacity: 0.4;
}

.stars {
  display: flex;
  align-items: center;
}

i.notranslate.material-icons.q-icon.icon-star {
  margin: 0 0.03vw !important;
}
// .icon-star{
//   margin: 0 .03vw !important;
// }

.reviews {
  display: flex;
  justify-content: space-between;
  position: relative;
}

.ribon {
  background-color: $secondary;
  color: white;
  font-size: 12px;
  width: 6vw;
  height: 3vh;
  display: flex;
  align-items: center;
  position: absolute;
  bottom: 43vh;
  left: -0.1vw;
}
.main-price {
  font-size: 20px;
  font-weight: 800;
  margin-top: 0;
  margin-bottom: 0;
  line-height: 4vh;
  display: flex;
  justify-content: flex-start;
}
.first-price {
  opacity: 0.2;
  font-size: 12px;
  font-weight: 800;
  display: flex;
  align-items: center;
  margin-left: 1vw;
  margin-top: 0;
  margin-bottom: 0;
}
.discounted-price {
  font-size: 20px;
  font-weight: 800;
  margin-top: 0;
  margin-bottom: 0;
  line-height: 4vh;
}
.price-combo {
  display: flex;
  justify-content: flex-start;
}

.img-product {
  width: 10vw;
  height: 20vh;
  margin-left: 5vw;
}
</style>
