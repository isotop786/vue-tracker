<template>

<div class="grid md:grid-cols-2 gap-4">
    <div class="flex flex-col shadow-md bg-blue-100 p-6 text-center rounded">
        <h3 class="text-3xl text-blue-900 font-bold mb-4 text-center rounded">
            Comfimed Cases
        </h3>
        <div class="text-2xl mb-4">
            <span class="text-center font-bold">
               New Cases: {{stats.NewConfirmed}}
            </span>
        </div>

        <div class="text-2xl mb-4">
            <span class="text-center font-bold">
                Total Cases : {{stats.TotalConfirmed}}
            </span>
        </div>
    </div>

    <!-- Deaths -->
    <div class="shadow-md bg-red-500 p-6 text-center rounded text-">
        <h3 class="text-3xl text-white font-bold mb-4 text-center rounded">
            Deaths 
        </h3>
        <div class="text-2xl mb-4">
            <span class="text-center font-bold text-white">
                New Death: {{stats.NewDeaths}}
            </span>
        </div>
        <div class="text-2xl mb-4">
            <span class="text-center font-bold text-white">
                Total Death: {{stats.TotalDeaths}}
            </span>
        </div>
    </div>

</div>
  <!-- <div class="grid grid-cols-3 ">
      <div class="flex flex-col justy-center items-stretch ">
         <p class="bg-yellow-300">New Confirmed: {{stats.NewConfirmed}}</p>
         <p>Total Confirmed: {{stats.TotalConfirmed}}</p>
         <p>New Death: {{stats.NewDeaths}}</p>
         <p>Total Death: {{stats.TotalDeaths}}</p>
         <p>New Recovered: {{stats.NewRecovered}}</p>
         <p>Total Recovered: {{stats.TotalRecovered}}</p>
      </div>
  </div> -->
</template>

<script>
export default {
    name:"DataBox",
    props:['stats']
}
</script>

<style>

</style>