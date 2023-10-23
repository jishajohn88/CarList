<!-- eslint-disable indent -->
<!-- eslint-disable no-trailing-spaces -->
<!-- eslint-disable vue/no-parsing-error -->
<template>
   <article>
    <div class="container">
        <div v-for="vehicle in vehicles" :key="vehicle.card_guid">
           <div class="vehicle_card">
                <img :src="vehicle.original_media_urls[0]" :alt="vehicle" width="100px" height="50px">
                <div class="vehicle_type">{{vehicle.advert_classification}}</div>
                <div class="vehicle_miles">{{vehicle.odometer_value}} miles</div>
                <div class="vehicle_body_type">{{vehicle.body_type}}</div>
                <p class="vehicle_card_plate">{{vehicle.plate}} {{vehicle.make}}</p>
                <span class="vehicle_card_derivative">{{vehicle.derivative}}</span>
                <p class="vehicle_price">£{{formatNumber(vehicle.original_price)}}</p>
            </div>
           </div>           
        </div>
   </article>
    
</template>

<script>
export default {
  data () {
    return {
      vehicles: [],
      result: []
    }
  },
  methods: {
    formatNumber (num) {
      return Math.round(num)
    }
  },
  mounted () {
    fetch('http://localhost:3000/data')
      .then((res) => res.json())
      .then(arrayOfObjects => {
        this.vehicles = arrayOfObjects
      })
      .catch(err => console.log(err.message))
  }

}
</script>

<style scoped>
    article{
        float: left;
        padding: 20px;
        width: 100%;
    }
    .container {
        margin: 0 auto;
        background: #eee;
        text-align: left;
        padding: 30px;
        border-radius: 10px;
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        flex-wrap: wrap;
    }
    .vehicle_card{
        display: block;
        margin: 4px;
        background: white;
        border-radius: 4px;
        align-content: flex-start;
        position:relative;
    }
    img {
        width: 200px;
        height: 150px;
        border-radius: 4px;
    }
    .vehicle_card_plate{
        font-size:12px;
        padding:4px;
        margin: 0 10px;
        text-align: left;
        font-weight: bold;
    }
    .vehicle_card_derivative {
        font-size: 10px;
        padding: 4px;
        margin: 0 10px;
    }
    .vehicle_price {
        font-size: 14px;
        font-weight: bold;
        padding:4px;
        margin: 0 10px;
    }
    .vehicle_type{
        position: absolute;
        top:8px;
        left: 8px;
        background: black;
        padding:4px;
        border-radius:4px;
        color: #eee;
        font-size: 10px;
    }
    .vehicle_miles{
        position: absolute;
        top: 120px;
        left: 16px;
        background: black;
        color:#eee;
        font-size: 10px;
        padding: 4px;
        border-radius: 4px;
    }
    .vehicle_body_type{
        position: absolute;
        top: 120px;
        left: 80px;
        background: black;
        color:#eee;
        font-size: 10px;
        padding: 4px;
        border-radius: 4px;
    }
</style>
