<template>
  <div id="app" >
    <div>
      <b-jumbotron >
        <Naslovnica/>
        
        <Pocetna/>
      </b-jumbotron>  
    </div>  
  </div>
</template>

<script>

import Pocetna from './components/Pocetna'
import Naslovnica from './components/Naslovnica'
export default {
  name: 'App',
  components: {
    Pocetna,
    Naslovnica
    
  }
}
</script>

<style>
  #app{
    background-color:darkgrey;
  
  }
</style>
