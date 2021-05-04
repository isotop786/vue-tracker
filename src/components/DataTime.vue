<template>
  <div class="text-center">
      <h2 class="text-2xl md:text-4xl font-bold text-gray-700">{{text}}</h2>
    <div class="text-xl md:text-2xl mt-2 md:mb-5 mb-3 md:mb-10 ">
        {{getDate}}
    </div>
  </div>
</template>

<script>
import moment from 'moment'
export default {
name:"DataTime",
props:['text','dataDate'],
computed:{
    getDate: function(){
        return moment(this.dataDate).format('Do MMMM, YYYY')
    }
}
}

</script>

<style>

</style>