<template>
  <specialPrice :itemPrice = product[selected].price :sale-perc="product[selected].salePercent" />
  <div class="card" :class="{'sold': product[selected].itemStock === 0}">
    <cardHeader :itemName = product[selected].name @change-selected="selected = $event" :productLength = product.length />
    <cardImage :imgPath1 = product[selected].img[0] :imgPath2 = product[selected].img[1] :imgPath3 = product[selected].img[2] />
    <cardContent :itemAbout = product[selected].about />
    <div class="display-flex">
      <cardPrice :itemPrice = product[selected].price :salePerc = product[selected].salePercent />
      <cardStock :itemStock= product[selected].stock />
    </div>
    <cardFooter />
  </div>
</template>

<script>
import SpecialPrice from "./components/specialPrice.vue";
import cardHeader from "./components/cardHeader.vue";
import cardImage from "./components/cardImage.vue";
import cardContent from "./components/cardContent.vue";
import CardPrice from "./components/cardPrice.vue";
import CardStock from "./components/cardStock.vue";
import CardFooter from "./components/cardFooter.vue";
export default {
  name: "app",
  components: {
    SpecialPrice,
    cardHeader,
    cardImage,
    cardContent,
    CardPrice,
    CardStock,
    CardFooter,
  },

  data() {
    return {
      selected: 0,
      product: [
        {
          id: 0,
          name: "Iphone 12 64 GB",
          img: ["src/assets/img/iphone12/1.jpg","src/assets/img/iphone12/2.jpg","src/assets/img/iphone12/3.jpg"],    
          about: "MPN: MGH63LL/A Style: Bar Network: Unlocked Features: Proximity Sensor, E-compass, Gyro Sensor, Accelerometer, Ambient Light Sensor, Barometer, Fingerprint Sensor, eSIM Operating System: iOS Camera Resolution: 12.0 MP, Storage Capacity: 64 GB Screen Size: 6.1 in Color: Black Model: Apple, iPhone 12 Brand: Apple Connectivity: 5G, Bluetooth, Wi-Fi, Lightning, NFC, Lock Status: Factory Unlocked Processor: Hexa Core Contract: Without",
          price: 1700,
          salePercent: 20,
          stock: 0,
        },
        {
          id: 1,
          name: "Iphone 11 64 GB",
          img: ["src/assets/img/iphone11/1.jpg","src/assets/img/iphone11/2.jpg","src/assets/img/iphone11/3.jpg"],
          about: "Brand:	Apple	Model:	Apple iPhone 11Storage Capacity:	64 GB	Network:	, Unlocked, Camera Resolution:	, 12.0 MP	, Screen Size:	, 6.1 in, Operating System:	, iOS	, Lock Status:	, Factory Unlocked, Connectivity:	, 4G, Bluetooth, Lightning, NFC, Wi-Fi	, Processor:	, Hexa Core, RAM:	, 4 GB	, Features:	, Dual Rear Cameras, Tap to Wake, Ultra Wide-Angle Camera, Manufacturer Color:	, Black, Green, Purple, (PRODUCT)RED, White, Yellow	, Bundled Items:	, Adapter, Cable, Release Date:	, 2019	, Battery Health/Capacity:	, 80% or higher",
          price: 2100,
          salePercent: 0,
          stock: 10,
        },
      ],
    }
  },
};

  
 


</script>

<style lang="css" scoped>
.display-flex {
  display: flex;
}

.card{
  margin-top: 10em;
}

.sold{
  opacity: 0.5;
}
</style>




