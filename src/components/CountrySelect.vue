<template>

     
     <select @change="onChange()" v-model="selected"
    class="form-select w-full block p-3 my-2 md:my-10 border rounded"
     > 
       <option value="0">Select Country</option>
       <option class="w-4" v-for="c in countries" :key="c.ID" :value="c.ID">{{c.Country}}</option>
     </select>
<!-- {{countries}} -->
</template>

<script>
export default {
name:"CountrySelect",
props:['countries'],
data(){
    return{
        selected:0
    }
},
methods:{
    onChange(){
        const country = this.countries.find((item)=> item.ID === this.selected)

        // console.log(country)

        this.$emit('get-country',country)
    }
}
}
</script>

<style>

</style>