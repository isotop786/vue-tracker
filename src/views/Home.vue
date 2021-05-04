<template>

    <main v-if="data">
      <DataTime :text="title" :dataDate="data.Date"/>
      <DataBox :stats="stats"/>

      <CountrySelect @get-country="setCountry" :countries="data.Countries" />
    
    <button
    v-if="stats.Country" @click="clearCountry"
     class="w-full mb-6 bg-blue-700 text-white rounded p-3 focus:outline-none hover:bg-blue-500 hover:text-black">Clear Country</button>
           
    
     </main>
    <main v-else class="flex flex-col align-center justify-center text-center">
      <div class="text-center text-gray-400 mb-4 ">
       <p class="font-bold">Loading Data...</p> 
        <img :src="loadingImage" alt="" class="w-24 m-auto mt-10">
      </div>
    </main>
       
  

</template>

<script>
// @ is an alias to /src
import DataTime from '../components/DataTime';
import DataBox from '@/components/DataBox';
import CountrySelect from '@/components/CountrySelect';
import Footer from '@/components/Footer'
export default {
  name: 'Home',
  components: {
    DataTime,
    DataBox,
    CountrySelect,
    Footer
  },
  data(){
    return{
      data: null,
      dataDate:'',
      stats: {},
      title:'Global',
      countries: [],
      loadingImage: require('../assets/loader.gif')

    }
  },
  methods:{
    async fetchApi(){

      const res = await fetch('https://api.covid19api.com/summary');
      const data = await res.json()
     
        return data
     
      
    },

    setCountry(country){
      // alert(country.Country)
      this.stats = country;
      this.title = country.Country
    },
    async clearCountry(){
      this.data = null 
      this.data = await this.fetchApi();
      this.stats = await this.data.Global
      this.title ='Global'
    }
  },
  async created(){
   this.data = await this.fetchApi()

    this.stats = await this.data.Global
    this.date = await this.data.Date

  //  console.log(this.data)
  }
}
</script>
