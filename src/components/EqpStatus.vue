<template>
	<div class="iu-fa-eqpstatus">
		<div v-if="m_status == 0" class="btn-secondary">离线</div>
		<div v-if="m_idle == 1" class="btn-warning">待机</div>
		<div v-if="m_run == 2" class="btn-success">运行</div>
		<div v-if="m_alarm == 4" class="btn-danger">报警</div>
		<div v-if="m_etime ==8" class="btn-info">调试</div>
		<div v-if="m_manu == 16" class="btn-primary">维护</div>
	</div>
</template>

<script>
	import Vue from 'vue';
	import {BootstrapVue} from 'bootstrap-vue';
	
	export default{
		name:'iuEqpStatus',
		data:function(){
			return {
				m_status : 0,
				m_idle:0,
				m_run:0,
				m_alarm:0,
				m_etime:0,
				m_manu:0
			}
		},
		watch:{
			m_status:function(val){
				this.m_idle = val&1;
				this.m_run = val&2;
				this.m_alarm = val&4;
				this.m_etime = val&8;
				this.m_manu = val&16;
			}
		},
		methods:{
			setStatus:function(val){
				this.m_status = val
			}
		},
		components:{
			
		}
	}
</script>

<style>
	.iu-fa-eqpstatus{
		width: 100px;		
		border: #BFBFBF 1px solid;
	}
</style>
