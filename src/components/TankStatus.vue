<template>
	<div class="r_out">
	<div class="r_in" ref="rr">
	<div class="r_c ct" :style="{height: m_percent+'%'}" v-if="m_percent > p_toplimit"></div>
	<div class="r_c cb" :style="{height: m_percent+'%'}" v-if="m_percent < p_bottomlimit"></div>
	<div class="r_c c0" :style="{height: m_percent+'%'}" v-if="(m_percent >= p_bottomlimit) & (m_percent <= p_toplimit) & (p_type == 0)"></div>
	<div class="r_c c1" :style="{height: m_percent+'%'}" v-if="(m_percent >= p_bottomlimit) & (m_percent <= p_toplimit) & (p_type == 1)"></div>
	<div class="r_c c2" :style="{height: m_percent+'%'}" v-if="(m_percent >= p_bottomlimit) & (m_percent <= p_toplimit) & (p_type == 2)"></div>
	<div class="r_c c3" :style="{height: m_percent+'%'}" v-if="(m_percent >= p_bottomlimit) & (m_percent <= p_toplimit) & (p_type == 3)"></div>
	<div class="r_num">{{m_percent}}%</div>
	</div>
	<p style="color:#f0f040;">{{p_name}}</p>
	</div>
</template>

<script>
	export default{
		name:'iuTankStatus',
		props:{
			p_toplimit:{
				type:Number,
				default:90
			},
			p_bottomlimit:{
				type:Number,
				default:10
			},
			p_type:{
				type:Number,
				default:0
			},
			p_name:{
				type:String,
				default:'未知'
			}
		},
		data:function(){
			return{
				m_percent : 0,				
			}
		},
		methods:{
			setTank:function(percent){
				this.m_percent = percent
				alert(this.$refs.rr.animate)
				
				
			}
		}
	}
</script>

<style>
	.r_out {width:60px; height:120px; border:6px solid #d9d9d9; background:#fff; box-shadow:3px 3px 5px #bfbfbf; -webkit-box-shadow:3px 3px 5px #bfbfbf; -moz-box-shadow:3px 3px 5px #bfbfbf; -ms-box-shadow:3px 3px 5px #bfbfbf; border-radius:50%; -webkit-border-radius:20%; -moz-border-radius:50%; -ms_border-radius:50%; display:inline-block; margin-right:50px; position:relative;}
	
	.r_out p {position:absolute; bottom:-40px; color:#000; text-align:center; margin:0 auto; width:100%; font-size:16px; line-height:1.5; font-weight:bold;}
	
	
	
	.r_in {width:50px; height:100px; border:5px solid #fff; border-radius:50%; -webkit-border-radius:20%; -moz-border-radius:50%; -ms_border-radius:50%; overflow:hidden; position:relative;}
	
	.r_c {width:50px;  position:absolute; bottom:0; left:0; }
	
	.c1 {background:#4040ff;}	
	.c2 {background:#87d7a5;}	
	.c0 {background:#00adc7;}
	.c3 {background:#4498a7;}
	
	.cb {background:#FFA511; }
	.ct {background:#dd2222;}
	.r_num {color:#404040; font-size:20px; line-height:1.5; font-weight:bold; position:absolute; top:50%; margin-top:-25px; text-align:center; width:100%;}
</style>
