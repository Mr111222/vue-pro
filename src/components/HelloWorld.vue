<template>
  <div class="lists">
  	<p>我是list</p>
  	<ul>
  		<li v-for="(i,index) in lists" :key="index">
  			{{i.text}}
  		</li>
  	</ul>
  </div>
</template>
<script type="text/ecmascript-6">
	import axios from "axios"
	export default {
	  data() {
	    return {
	      lists: []
	    };
	  },
	  created() {
	    this.$http.get('/lists').then((res) => {
	    	console.log(res.data)
	        this.lists = res.data.data;
	    });
	  }
	};
</script>
