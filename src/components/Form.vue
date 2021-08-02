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
        <form action="#" method="POST">
          <div class="shadow overflow-hidden sm:rounded-md">
            <div class="px-4 py-5 bg-white sm:p-6">
              <div class="grid grid-cols-6 gap-6">

                <div class="col-span-6 sm:col-span-3">
                  <label for="type" class="block text-sm font-medium text-gray-700">Type</label>
                  <select v-model="type" id="type" name="type" autocomplete="type" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>House</option>
                    <option>Apartment</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="rooms" class="block text-sm font-medium text-gray-700">Rooms</label>
                  <select v-model="rooms" id="rooms" name="rooms" autocomplete="rooms" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
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
                  <input v-model="surface" type="number" min=0 name="surface" id="surface" autocomplete="surface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="facade" class="block text-sm font-medium text-gray-700">Façades</label>
                  <select v-model="facade" id="facade" name="facade" autocomplete="facade" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
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
                  <select v-model="kitchen" id="kitchen" name="kitchen" autocomplete="kitchen" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>Not Equipped</option>
                    <option>Equipped</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="furnished" class="block text-sm font-medium text-gray-700">Furnished</label>
                  <select v-model="furnished" id="furnished" name="furnished" autocomplete="furnished" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>Not furnished</option>
                    <option>Furnished</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="terrace" class="block text-sm font-medium text-gray-700">Terrace</label>
                  <select v-model="terrace" id="terrace" name="terrace" autocomplete="terrace" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>Without terrace</option>
                    <option>With terrace</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="terraceSurface" class="block text-sm font-medium text-gray-700">Terrace surface m<sup>2</sup></label>
                  <input v-model="terraceSurface" type="text" name="terraceSurface" id="terraceSurface" autocomplete="terraceSurface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="garden" class="block text-sm font-medium text-gray-700">Garden</label>
                  <select v-model="garden" id="garden" name="garden" autocomplete="garden" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>Without garden</option>
                    <option>With garden</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="gardenSurface" class="block text-sm font-medium text-gray-700">Garden surface m<sup>2</sup></label>
                  <input v-model="gardenSurface" type="text" name="gardenSurface" id="gardenSurface" autocomplete="gardenSurface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="totalSurface" class="block text-sm font-medium text-gray-700">Total land surface m<sup>2</sup></label>
                  <input v-model="totalSurface" type="text" name="totalSurface" id="totalSurface" autocomplete="totalSurface" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-gray-700 rounded-md" />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="pool" class="block text-sm font-medium text-gray-700">Swimming Pool</label>
                  <select v-model="pool" id="pool" name="pool" autocomplete="pool" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>Without pool</option>
                    <option>With pool</option>
                  </select>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label for="condition" class="block text-sm font-medium text-gray-700">Condition of the building</label>
                  <select v-model="condition" id="condition" name="condition" autocomplete="condition" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
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
                  <select v-model="province" id="province" name="province" autocomplete="province" class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                    <option>Luxembourg</option>
                    <option>Hainaut</option>
                    <option>Flandre-Occidentale</option>
                    <option>Liege</option>
                    <option>Flandre-Orientale</option>
                    <option>Bruxelles</option>
                    <option>Brabant Flamand</option>
                    <option>Anvers</option>
                    <option>Brabant Wallon</option>
                    <option>Limbourg</option>
                    <option>Namur</option>
                    <option></option>



                    <option>Wallonia</option>
                    <option>Flanders</option>
                    <option>Brussels</option>
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
        <h2>{{ type }} with {{rooms}} and a surface of
      {{surface}}m<sup>2</sup>. The place has 
      {{facade}} facasdes and comes {{pool}}. There is {{terrace}} of {{terraceSurface}}m<sup>2</sup>. The kitchen is
      {{kitchen}} and the house is {{furnished}}. There is a {{garden}} of {{gardenSurface}}m<sup>2</sup>. The total surface of the property is {{totalSurface}}.
      The condition is {{condition}}. It's located in {{province}}</h2>

      </div>
    </div>
  </div>

</template>

<script>

export default {
  data(){
    return{
      type: '',
      rooms: '',
      surface: '',
      facade: '',
      kitchen: '',
      furnished: '',
      terrace: '',
      terraceSurface: '',
      garden: '',
      gardenSurface: '',
      totalSurface: '',
      pool: '',
      condition: '',
      province: ''

    }
  }
}
</script>