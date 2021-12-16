<template>
  <div class="card" :class="productClasses">
    <cardHeader
      :item-name="product[selected].name"
      @change-selected="selected = $event"
      :product-length="product.length"
    ></cardHeader>
    <cardImage :img-path="product[selected].img" />
    <cardContent :item-about="product[selected].about" />
    <div class="display-flex">
      <cardPrice
        :item-price="product[selected].price"
        :sale-perc="product[selected].salePercentage"
      />
      <cardStock :item-stock="product[selected].stock" />
    </div>
    <cardFooter />
  </div>
  <specialPrice
    :item-price="product[selected].price"
    :sale-perc="product[selected].salePercentage"
  />
</template>

<script>
import specialPrice from "./components/specialPrice.vue";
import cardHeader from "./components/cardHeader.vue";
import cardImage from "./components/cardImage.vue";
import cardContent from "./components/cardContent.vue";
import cardPrice from "./components/cardPrice.vue";
import cardStock from "./components/cardStock.vue";
import cardFooter from "./components/cardFooter.vue";
export default {
  name: "app",
  components: {
    specialPrice,
    cardHeader,
    cardImage,
    cardContent,
    cardPrice,
    cardStock,
    cardFooter,
  },

  data() {
    return {
      selected: 0,
      product: [
        {
          id: 0,
          name: "Iphone 12 64 GB",
          img: [
            {
              id: 0,
              src: "src/assets/img/iphone12/1.jpg",
            },
            {
              id: 1,
              src: "src/assets/img/iphone12/2.jpg",
            },
            {
              id: 2,
              src: "src/assets/img/iphone12/3.jpg",
            },
          ],
          about:
            "MPN: MGH63LL/A Style: Bar Network: Unlocked Features: Proximity Sensor, E-compass, Gyro Sensor, Accelerometer, Ambient Light Sensor, Barometer, Fingerprint Sensor, eSIM Operating System: iOS Camera Resolution: 12.0 MP, Storage Capacity: 64 GB Screen Size: 6.1 in Color: Black Model: Apple, iPhone 12 Brand: Apple Connectivity: 5G, Bluetooth, Wi-Fi, Lightning, NFC, Lock Status: Factory Unlocked Processor: Hexa Core Contract: Without",
          price: 1700,
          salePercentage: 12,
          stock: 5,
        },
        {
          id: 1,
          name: "Iphone 11 64 GB",
          img: [
            {
              id: 0,
              src: "src/assets/img/iphone11/1.jpg",
            },
            {
              id: 1,
              src: "src/assets/img/iphone11/2.jpg",
            },
            {
              id: 3,
              src: "src/assets/img/iphone11/3.jpg",
            },
          ],
          about:
            "Brand:	<b>Apple	Model</b>:	Apple iPhone 11 Storage Capacity:	64 GB	Network:	, Unlocked, Camera Resolution:	, 12.0 MP	, Screen Size:	, 6.1 in, Operating System:	, iOS	, Lock Status:	, Factory Unlocked, Connectivity:	, 4G, Bluetooth, Lightning, NFC, Wi-Fi	, Processor:	, Hexa Core, RAM:	, 4 GB	, Features:	, Dual Rear Cameras, Tap to Wake, Ultra Wide-Angle Camera, Manufacturer Color:	, Black, Green, Purple, (PRODUCT)RED, White, Yellow	, Bundled Items:	, Adapter, Cable, Release Date:	, 2019	, Battery Health/Capacity:	, 80% or higher",
          price: 2100,
          salePercentage: 0,
          stock: 0,
        },
      ],
    };
  },
  computed: {
    productClasses() {
      if (this.product[this.selected].stock === 0) {
        return "sold";
      }
    },
  },
};
</script>

<style lang="css" scoped>
.display-flex {
  display: flex;
}

.card {
  margin-top: 5rem;
}

.sold {
  opacity: 0.5;
}
</style>




