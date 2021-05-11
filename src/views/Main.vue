<template>
 


<h2>Main page</h2>
<div class="container">
	<div class="single-show">
		<div v-for="inf in info" :key="inf" id="app">
			<ul>
				<li>{{ inf.name }}</li>
				<li>{{ inf.type }}</li>
				<li>{{ inf.language }}</li>
				<li>{{ inf.genrs }}</li>
				<li>{{ inf.summary }}</li>
				<li>{{ inf.timezone }}</li>
				<li></li>
			</ul>
  
  
  
    
  
</div>
	</div>
</div>







</template>

<script>
// @ is an alias to /src
  import axios from 'axios'


export default {
  data() {
    return {
      info: null,
      isOpen: false
    }
  },
  methods: {
    toggleModal() {
      this.isOpen = !this.isOpen
    }
  },
  mounted () {
    axios
      .get('https://api.tvmaze.com/singlesearch/shows?q=girls')
      // You can change the link above to your API
      // Note: I've found it sometimes only works with HTTPS
      .then(response => (this.info = response))
  }
}
</script>
<style>
	.single-show {
		width: 1100px;
		height: 300px;
		opacity: 0.3;
		background: #D6D8E7;
		border-radius: 20px;
		font-family: Roboto-Medium;
		font-size: 20px;
		color: rgba(0,0,0,0.87);
		text-align: left;
		font-family: Roboto-Medium;
		font-size: 12px;
		color: rgba(0,0,0,0.87);
		text-align: left;
		opacity: 0.12;
		background: #D6D8E7;
		border-radius: 6px;
		opacity: 0.7;
	}
</style>