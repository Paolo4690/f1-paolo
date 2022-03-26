<template>
  <div id="app">
    <header-f-1 
      :arrDriver= arrDriver
      :arrTeam= arrTeam
       />
  </div>
</template>

<script>
import HeaderF1 from './components/HeaderF1.vue'

import axios from 'axios'

export default {
  name: 'App',
  data () {
    return {
      arrDriver: null,
      arrTeam: null
    }
  },
  components: {
    HeaderF1
  },
  created () {
    axios.get('https://ergast.com/api/f1/current/drivers.json')
      .then((response) => {
        this.arrDriver = response.data.MRData.DriverTable.Drivers
      })
    axios.get('http://ergast.com/api/f1/current/constructors.json')
      .then((response) => {
        this.arrTeam = response.data.MRData.ConstructorTable.Constructors
      })
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Titillium+Web:wght@200;300;400;600;700&display=swap');
$primary: #e10600;
$secondary: #1e2d3b;
$text-light:#fff;
@import '~bootstrap/scss/bootstrap';
body {
font-family: 'Titillium Web', sans-serif;
}

</style>
