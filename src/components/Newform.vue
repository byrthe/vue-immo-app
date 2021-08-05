<template>
    <div class="mt-10 sm:mt-0">
        <div class="p-10 font-medium text-lg">
          <p>Fill in the form and get an estimation for the current value of your property.</p>
        </div>

        <!-- FORM NEW -->
        <!--<form method="POST" @submit="predictPrice">-->
        <form>

          <div class="shadow overflow-hidden sm:rounded-md">
            <div class="px-4 py-5 bg-white sm:p-6">
              <div class="grid grid-cols-6 gap-6">

                <div class="col-span-6 sm:col-span-3">
                  <label for="type" class="block text-sm font-medium text-gray-700">Type</label>
                  <select v-model="type" id="type" name="type" autocomplete="type" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option value="HOUSE">House</option>
                    <option value="APARTMENT">Apartment</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="room_numer" class="block text-sm font-medium text-gray-700">Rooms</label>
                  <select v-model="room_number" id="room_number" name="room_number" autocomplete="room_number" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                    <option value="5">5</option>
                    <option value="6">6</option>
                    <option>7</option>
                    <option :value="8">8</option>
                    <option :value="9">9</option>
                    <option :value="10">10</option>
                    <option :value="11">11</option>
                    <option :value="12">12</option>
                    <option :value="13">13</option>
                    <option :value="14">14</option>
                    <option :value="15">15</option>
                  </select>
                </div>


                <div class="col-span-6 sm:col-span-3">
                  <label for="area" class="block text-sm font-medium text-gray-700">Surface m<sup>2</sup></label>
                  <input v-model="area" number step="1" min=0 name="area" id="area" autocomplete="area" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md p-2" style="--tw-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.5);" />
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
                  <label for="kitchen_equipped" class="block text-sm font-medium text-gray-700">Kitchen</label>
                  <select v-model="kitchen_equipped" id="kitchen_equipped" name="kitchen_equipped" autocomplete="kitchen_equipped" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="0">Not equipped</option>
                    <option :value="1">Equipped</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="fireplace" class="block text-sm font-medium text-gray-700">Fireplace</label>
                  <select v-model="fireplace" id="fireplace" name="fireplace" autocomplete="fireplace" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="0">No fireplace</option>
                    <option :value="1">With a fireplace</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="furnished" class="block text-sm font-medium text-gray-700">Furnished</label>
                  <select v-model="furnished" id="furnished" name="furnished" autocomplete="furnished" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="0">Not furnished</option>
                    <option :value="1">Furnished</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="swimming_pool" class="block text-sm font-medium text-gray-700">Swimming Pool</label>
                  <select v-model="swimming_pool" number step="1" id="swimming_pool" name="swimming_pool" autocomplete="pool" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="0">No swimming pool</option>
                    <option :value="1">With a swimming pool</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="terrace" class="block text-sm font-medium text-gray-700">Terrace</label>
                  <select v-model="terrace" id="terrace" name="terrace" autocomplete="terrace" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="0">No terrace</option>
                    <option :value="1">With a terrace</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <div v-show="terrace">
                    <label for="terrace_area" class="block text-sm font-medium text-gray-700">Terrace surface m<sup>2</sup></label>
                    <input v-model="terrace_area" number step="1" name="terrace_area" id="terrace_area" autocomplete="terrace_area" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-900 rounded-md p-2" style="--tw-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.5);" />
                  </div>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="garden" class="block text-sm font-medium text-gray-700">Garden</label>
                  <select v-model="garden" id="garden" name="garden" autocomplete="garden" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="0">No garden</option>
                    <option :value="1">With a garden</option>                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <div v-show="garden">
                    <label for="garden_area" class="block text-sm font-medium text-gray-700">Garden surface m<sup>2</sup></label>
                    <input v-model="garden_area" number step="1" name="garden_area" id="garden_area" autocomplete="garden_area" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md p-2" style="--tw-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.5);" />
                  </div>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="land_surface" class="block text-sm font-medium text-gray-700">Total land surface m<sup>2</sup></label>
                  <input v-model="land_surface" number step="1" name="land_surface" id="land_urface" autocomplete="land_surface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md p-2" style="--tw-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.5);" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="building_condition" class="block text-sm font-medium text-gray-700">Condition of the building</label>
                  <select v-model="building_condition" id="building_condition" name="building_condition" autocomplete="building_condition" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option value="TO_BE_DONE_UP">to be done up</option>
                    <option value="TO_RENOVATE">to renovate</option>
                    <option value="GOOD">good</option>
                    <option value="JUST_RENOVATED">just renovated</option>
                    <option value="AS_NEW">as new</option>
                    <option value="TO_RESTORE">to restore</option>
                  </select>
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label for="Province" class="block text-sm font-medium text-gray-700">Province</label>
                  <select v-model="Province" id="Province" name="Province" autocomplete="Province" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option value="LUXEMBOURG">Luxembourg</option>
                    <option value="HAINAUT">Hainaut</option>
                    <option value="FLANDRE_OCCIDENTALE">Flanders Occidentale</option>
                    <option value="FLANDRE_ORIENTALE">Flanders Orientale</option>
                    <option value="LIEGE">Liège</option>
                    <option value="BRABANT_FLAMAND">Flemish Brabant</option>
                    <option value="BRABANT_WALLON">Walloon Brabant</option>
                    <option value="BRUXELLES">Brussels</option>
                    <option value="ANVERS">Antwerp</option>
                    <option value="LIMBOURG">Limburg</option>
                    <option value="NAMUR">Namur</option>
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
        <div class="estimation md:flex bg-white rounded-xl p-8 md:p-6 justify-center" v-if="Price != 0">
            <h1 class="text-lg">We estimate a price of around <b>€{{ Price }}</b> for your property in {{ Province }}</h1>
        </div>
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
            facade_count:1,
            swimming_pool:0,
            building_condition: 'GOOD',
            Province:'BRUXELLES',
            Price: 0
      
    }
  },
  methods: {
    async addContent(event){
        event.preventDefault();
        let result = await axios.post("https://flaskapimo.herokuapp.com/predict", {"type": this.type,
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
        this.Price = Math.round(JSON.parse(result.request.response).Price[0]);
        console.log(this.Price);
    },

// this one works with test data ! wrong link !
    // async addContent(){
    //     let result = await axios.post("https://bappimmoo.herokuapp.com/predict", {"type": "APARTMENT","room_number":2,"area": 50,"kitchen_equipped_equipped":1,"furnished":0,"fireplace": 0, "terrace":1,"terrace_area":18,"garden":1,"garden_area":20,"land_surface":120,"facade_count":4,"swimming_pool":0,"building_condition": "GOOD","Province":"BRUXELLES"});
    //     console.log(result.request.response);
    //     console.log('function called', this.typo, this.surfa);
    // },
  }
}

// type: this.type >>> in de method wanneer values ophalen  
</script>

<style>
    .estimation{
        margin-top:50px;
    }
</style>