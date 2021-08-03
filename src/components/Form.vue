<template>
    <div class="mt-10 sm:mt-0">
    <div class="md:grid md:grid-cols-3 md:gap-6">
      <!-- <div class="md:col-span-1">
        <div class="px-4 sm:px-0">
          <h3 class="text-lg font-medium leading-6 text-gray-900">Personal Information</h3>
          <p class="mt-1 text-sm text-gray-600">
            Use a permanent address where you can receive mail.
          </p>
        </div>
      </div>-->
      <div class="mt-5 md:mt-0 md:col-span-12">

        <!-- FORM -->
        <form action="#" method="POST" @submit="postData">

          <div class="shadow overflow-hidden sm:rounded-md">
            <div class="px-4 py-5 bg-white sm:p-6">
              <div class="grid grid-cols-6 gap-6">

                <div class="col-span-6 sm:col-span-3">
                  <label for="type" class="block text-sm font-medium text-gray-700">Type</label>
                  <select v-model="posts.type" id="type" name="type" autocomplete="type" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="HOUSE">House</option>
                    <option :value="APARTMENT">Apartment</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="rooms" class="block text-sm font-medium text-gray-700">Rooms</label>
                  <select v-model="posts.rooms" id="rooms" name="rooms" autocomplete="rooms" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>1 room</option>
                    <option>2 rooms</option>
                    <option>3 rooms</option>
                    <option>4 rooms</option>
                    <option>5 rooms</option>
                    <option>6 rooms</option>
                    <option>7 rooms</option>
                    <option>8 rooms</option>
                    <option>9 rooms</option>
                    <option>10 rooms</option>
                    <option>11 rooms</option>
                    <option>12 rooms</option>
                    <option>13 rooms</option>
                    <option>14 rooms</option>
                    <option>15 rooms</option>
                  </select>
                </div>


                <div class="col-span-6 sm:col-span-3">
                  <label for="surface" class="block text-sm font-medium text-gray-700">Surface m<sup>2</sup></label>
                  <input v-model="posts.surface" number min=0 name="surface" id="surface" autocomplete="surface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="facade" class="block text-sm font-medium text-gray-700">Façades</label>
                  <select v-model="posts.facade" id="facade" name="facade" autocomplete="facade" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>1</option>
                    <option>2</option>
                    <option>3</option>
                    <option>4</option>
                    <option>5</option>
                    <option>6</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="kitchen" class="block text-sm font-medium text-gray-700">Kitchen</label>
                  <select v-model="posts.kitchen" id="kitchen" name="kitchen" autocomplete="kitchen" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value='false'>Not Equipped</option>
                    <option :value='true'>Equipped</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="furnished" class="block text-sm font-medium text-gray-700">Furnished</label>
                  <select v-model="posts.furnished" id="furnished" name="furnished" autocomplete="furnished" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value='false'>Not furnished</option>
                    <option :value='true'>Furnished</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="terrace" class="block text-sm font-medium text-gray-700">Terrace</label>
                  <select v-model="posts.terrace" id="terrace" name="terrace" autocomplete="terrace" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value='false'>Without terrace</option>
                    <option :value='true'>With terrace</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="terraceSurface" class="block text-sm font-medium text-gray-700">Terrace surface m<sup>2</sup></label>
                  <input v-model="posts.terraceSurface" number type="text" name="terraceSurface" id="terraceSurface" autocomplete="terraceSurface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="garden" class="block text-sm font-medium text-gray-700">Garden</label>
                  <select v-model="posts.garden" id="garden" name="garden" autocomplete="garden" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value='false'>Without garden</option>
                    <option :value='true'>With garden</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="gardenSurface" class="block text-sm font-medium text-gray-700">Garden surface m<sup>2</sup></label>
                  <input v-model="posts.gardenSurface" number type="text" name="gardenSurface" id="gardenSurface" autocomplete="gardenSurface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="totalSurface" class="block text-sm font-medium text-gray-700">Total land surface m<sup>2</sup></label>
                  <input v-model="posts.totalSurface" number type="text" name="totalSurface" id="totalSurface" autocomplete="totalSurface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="pool" class="block text-sm font-medium text-gray-700">Swimming Pool</label>
                  <select v-model="posts.pool" id="pool" name="pool" autocomplete="pool" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value='false'>Without pool</option>
                    <option :value='true'>With pool</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="condition" class="block text-sm font-medium text-gray-700">Condition of the building</label>
                  <select v-model="posts.condition" id="condition" name="condition" autocomplete="condition" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>To restore</option>
                    <option>As new</option>
                    <option>Just renovated</option>
                    <option>Good</option>
                    <option>To rennovate</option>
                    <option>To be done up</option>
                  </select>
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label for="province" class="block text-sm font-medium text-gray-700">Province</label>
                  <select v-model="posts.province" id="province" name="province" autocomplete="province" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option :value="LUXEMBOURG">Luxembourg</option>
                    <option :value="HAINAUT">Hainaut</option>
                    <option :value="FLANDRE-OCCIDENTALE">Flandre-Occidentale</option>
                    <option :value="LIEGE">Liege</option>
                    <option :value="FLANDRE-ORIENTALE">Flandre-Orientale</option>
                    <option :value="BRUXELLES">Bruxelles</option>
                    <option :value="BRABANT-FLAMAND">Brabant Flamand</option>
                    <option :value="ANVERS">Anvers</option>
                    <option :value="BRABANT-WALLON">Brabant Wallon</option>
                    <option :value="LIMBOURG">Limbourg</option>
                    <option :value="NAMUR">Namur</option>
                    <option></option>
                  </select>
                </div>
              </div>
            </div>
            <div class="px-4 py-3 bg-gray-50 text-right sm:px-6">
              <button type="submit" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                Estimate Price
              </button>
            </div>
          </div>
        </form>

        <h2>You have a</h2>
        <h2><b>{{ posts.type }}</b> with <b>{{posts.rooms}}</b> and a surface of
      <b>{{posts.surface}}</b>m<sup>2</sup>. The place has 
      <b>{{posts.facade}}</b> facasdes and comes <b>{{posts.pool}}</b>. There is <b>{{posts.terrace}}</b> of <b>{{posts.terraceSurface}}</b>m<sup>2</sup>. The kitchen is <b>{{posts.kitchen}}</b> and the house is <b>{{posts.furnished}}</b>. There is a {{posts.garden}} of <b>{{posts.gardenSurface}}</b>m<sup>2</sup>. The total surface of the property is <b>{{posts.totalSurface}}</b>.
      The condition is <b>{{posts.condition}}</b>. It's located in <b>{{posts.province}}</b></h2>
      </div>
      <form>  
        <label for="typo">type</label>
        <input type="text" name="typo" v-model="typo" style="border: 1px solid blue"/><br>
        <label for="typo">surface</label>
        <input type="text" name="surfa" v-model="surfa" style="border: 1px solid blue"/>
        <button v-on:click="addContent()">add content</button>
      </form>
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
      typo: '',
      surfa: '',
      posts: {type: null,
        rooms: null,
        surface: null,
        facade: null,
        kitchen: false,
        furnished: false,
        terrace: false,
        terraceSurface: null,
        garden: false,
        gardenSurface: null,
        totalSurface: null,
        pool: false,
        condition: null,
        province: null
        }
    }
  },
  methods: {
    addContent(){
      console.log('function called');
    },
    postData(e){
      this.axios.post('https://bappimmo.herokuapp.com/predict', this.posts)
      .then ((result)=>{
          console.warn(result);
      })
      e.preventDefault();
    }
  }
}
</script>