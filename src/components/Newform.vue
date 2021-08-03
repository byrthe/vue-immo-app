<template>
    <div class="mt-10 sm:mt-0">
      
        <!-- <label for="typo">type </label>
        <input type="text" name="typo" v-model="typo" style="border: 1px solid blue"/><br><br>
        

        <button type="submit" v-on:click="addContent" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">Estimate</button>
         -->

    <hr>

        <!-- FORM NEW -->
        <!--<form method="POST" @submit="predictPrice">-->
        <form>

          <div class="shadow overflow-hidden sm:rounded-md">
            <div class="px-4 py-5 bg-white sm:p-6">
              <div class="grid grid-cols-6 gap-6">

                <div class="col-span-6 sm:col-span-3">
                  <label for="type" class="block text-sm font-medium text-gray-700">Type</label>
                  <select v-model="type" id="type" name="type" autocomplete="type" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>HOUSE</option>
                    <option>APARTMENT</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="room_numer" class="block text-sm font-medium text-gray-700">Rooms</label>
                  <select v-model="room_number" id="room_number" name="room_number" autocomplete="room_number" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>1</option>
                    <option>2</option>
                    <option>3</option>
                    <option>4</option>
                    <option>5</option>
                    <option>6</option>
                    <option>7</option>
                    <option>8</option>
                    <option>9</option>
                    <option>10</option>
                    <option>11</option>
                    <option>12</option>
                    <option>13</option>
                    <option>14</option>
                    <option>15</option>
                  </select>
                </div>


                <div class="col-span-6 sm:col-span-3">
                  <label for="area" class="block text-sm font-medium text-gray-700">Surface m<sup>2</sup></label>
                  <input v-model="area" number step="1" min=0 name="area" id="area" autocomplete="area" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="facade_count" class="block text-sm font-medium text-gray-700">Façades</label>
                  <select v-model="facade_count" id="facade_count" name="facade_count" autocomplete="facade_count" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>1</option>
                    <option>2</option>
                    <option>3</option>
                    <option>4</option>
                    <option>5</option>
                    <option>6</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="kitchen_equipped" class="block text-sm font-medium text-gray-700">kitchen_equipped</label>
                  <select v-model="kitchen_equipped" id="kitchen_equipped" name="kitchen_equipped" autocomplete="kitchen_equipped" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>0</option>
                    <option>1</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="fireplace" class="block text-sm font-medium text-gray-700">Fireplace</label>
                  <select v-model="fireplace" id="fireplace" name="fireplace" autocomplete="fireplace" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>0</option>
                    <option>1</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="furnished" class="block text-sm font-medium text-gray-700">Furnished</label>
                  <select v-model="furnished" id="furnished" name="furnished" autocomplete="furnished" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>0</option>
                    <option>1</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="terrace" class="block text-sm font-medium text-gray-700">Terrace</label>
                  <select v-model="terrace" id="terrace" name="terrace" autocomplete="terrace" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>0</option>
                    <option>1</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="terrace_area" class="block text-sm font-medium text-gray-700">Terrace surface m<sup>2</sup></label>
                  <input v-model="terrace_area" number step="1" name="terrace_area" id="terrace_area" autocomplete="terrace_area" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="garden" class="block text-sm font-medium text-gray-700">Garden</label>
                  <select v-model="garden" id="garden" name="garden" autocomplete="garden" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>0</option>
                    <option>1</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="garden_area" class="block text-sm font-medium text-gray-700">Garden surface m<sup>2</sup></label>
                  <input v-model="garden_area" number step="1" name="garden_area" id="garden_area" autocomplete="garden_area" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="land_surface" class="block text-sm font-medium text-gray-700">Total land surface m<sup>2</sup></label>
                  <input v-model="land_surface" number step="1" name="land_surface" id="land_urface" autocomplete="land_surface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="swimming_pool" class="block text-sm font-medium text-gray-700">Swimming Pool</label>
                  <select v-model="swimming_pool" number step="1" id="swimming_pool" name="swimming_pool" autocomplete="pool" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="0">false</option>
                    <option :value="1">true</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="building_condition" class="block text-sm font-medium text-gray-700">Condition of the building</label>
                  <select v-model="building_condition" id="building_condition" name="building_condition" autocomplete="building_condition" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>TO_BE_DONE_UP</option>
                    <option>TO_RENOVATE</option>
                    <option>GOOD</option>
                    <option>JUST_RENOVATED</option>
                    <option>AS_NEW</option>
                    <option>TO_RESTORE</option>
                  </select>
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label for="province" class="block text-sm font-medium text-gray-700">Province</label>
                  <select v-model="Province" id="Province" name="province" autocomplete="province" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>LUXEMBOURG</option>
                    <option>HAINAUT</option>
                    <option>FLANDRE-OCCIDENTALE</option>
                    <option>FLANDRE-ORIENTALE</option>
                    <option>LIEGE</option>
                    <option>FLANDRE-ORIENTALE</option>
                    <option>BRUXELLES</option>
                    <option>ANVERS</option>
                    <option>LIMBOURG</option>
                    <option>NAMUR</option>
                  </select>
                </div>
              </div>
            </div>
            <div class="px-4 py-3 bg-gray-50 text-right sm:px-6">
              <button type="submit" v-on:click="addContent" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                Estimate Price
              </button>
            </div>

          </div>
        </form>
        <p v-if="Price != 0">Estimation: {{ Price }}</p>
  </div>
</template>

<script>
import * as Vue from 'vue' // in Vue 3
import axios from 'axios'
import VueAxios from 'vue-axios'

export default {
  data(){
    return{
            type: 'HOUSE',
            room_number: 1,
            area: 0,
            kitchen_equipped: 0,
            furnished:0,
            fireplace: 0, 
            terrace:0,
            terrace_area:0,
            garden:0,
            garden_area:0,
            land_surface:0,
            facade_count:0,
            swimming_pool:0,
            building_condition: 'GOOD',
            Province:'BRUXELLES',
            Price: 0
      
    }
  },
  methods: {
    async addContent(event){
        event.preventDefault();
        let result = await axios.post("https://bappimmoo.herokuapp.com/predict", {"type": this.type,
            "room_number": this.room_number,
            "area": this.area,
            "kitchen_equipped_equipped": this.kitchen_equipped_equipped,
            "furnished":this.furnished,
            "fireplace": this.fireplace, 
            "terrace":this.terrace,
            "terrace_area":this.terrace_area,
            "garden":this.garden,
            "garden_area":this.garden_area,
            "land_surface":this.land_surface,
            "facade_count":this.facade_count,
            "swimming_pool":this.swimming_pool,
            "building_condition": this.building_condition,
            "Province":this.Province});
        console.log(JSON.parse(result.request.response).Price[0]);
        console.log('function called');
        this.Price = JSON.parse(result.request.response).Price[0];
        console.log(this.Price);
    },

// this one works
    // async addContent(){
    //     let result = await axios.post("https://bappimmoo.herokuapp.com/predict", {"type": "APARTMENT","room_number":2,"area": 50,"kitchen_equipped_equipped":1,"furnished":0,"fireplace": 0, "terrace":1,"terrace_area":18,"garden":1,"garden_area":20,"land_surface":120,"facade_count":4,"swimming_pool":0,"building_condition": "GOOD","Province":"BRUXELLES"});
    //     console.log(result.request.response);
    //     console.log('function called', this.typo, this.surfa);
    // },


    async predictPrice(){
        let result = await axios.post("https://bappimmoo.herokuapp.com/predict", {"type": "APARTMENT","room_number":2,"area": 50,"kitchen_equipped_equipped":1,"furnished":0,"fireplace": 0, "terrace":1,"terrace_area":18,"garden":1,"garden_area":20,"land_surface":120,"facade_count":4,"swimming_pool":0,"building_condition": "GOOD","Province":"BRUXELLES"});
        
        console.log(result.request.response);
        console.log('predictPrice is called');
        
        // this.data
        
        // {
            // "type": this.data.type,
            // "room_number": this.data.room_number,
            // "area": this.data.area,
            // "kitchen_equipped_equipped": this.data.kitchen_equipped_equipped,
            // "furnished":this.data.furnished,
            // "fireplace": this.data.fireplace, 
            // "terrace":this.data.terrace,
            // "terrace_area":this.data.terrace_area,
            // "garden":this.data.garden,
            // "garden_area":this.data.garden_area,
            // "land_surface":this.data.land_surface,
            // "facade_count":this.data.facade_count,
            // "swimming_pool":this.data.swimming_pool,
            // "building_condition": this.data.building_condition,
            // "Province":this.data.Province
        // }
    //     )
    //     .then ((result)=>{
    //       console.log('Predict Price function callin', result.request.response);
    //   })
        console.log('Predict second call', this.type, this.Province);
    }
  }
}

// type: this.type >>> in de method wanneer values ophalen  
</script>
