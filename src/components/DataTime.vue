<template>
  <div class="text-center">
      <h2 class="text-4xl font-bold text-gray-700">{{text}}</h2>
    <div class="text-2xl mt-4 md:mb-5 mb-10 ">
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