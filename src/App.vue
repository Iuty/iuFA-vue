<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <iu-EqpStatus ref="demoStatus"/>
	<iu-TankStatus ref="demoTank"></iu-TankStatus>
  </div>
</template>

<script>

import iuEqpStatus from './components/EqpStatus.vue'
import iuTankStatus from './components/TankStatus.vue'

export default {
  name: 'app',
  components: {
	'iu-TankStatus':iuTankStatus,
    'iu-EqpStatus':iuEqpStatus,
  },
  methods:{
	  timerout:function(){
		  
	  }
  },
  mounted:function(){
	  this.$refs.demoStatus.setStatus(16);
	  this.$refs.demoTank.setTank(27);
	  //this.$refs.demoTank.setTank(99);
	  
	  
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
