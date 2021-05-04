<template>

  <Header/>

<div class="container">
      <router-view/>
</div>
<Footer/>
</template>


<script>
import Header from '../src/components/Header';
import Footer from '@/components/Footer'
export default {
  name:"App",
  components:{
    Header,
    Footer
  }
}
</script>


<style>
  
</style>