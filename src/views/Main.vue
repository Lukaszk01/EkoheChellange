<template>
<h2>Main page</h2>
<i class="fab fa-facebook-f"></i>
<div class="container">
	<div class="single-show">
		<div class="row">
			<div class="image">
			<img class="img d-flex justify-content-start" src="https://static.tvmaze.com/uploads/images/original_untouched/31/78286.jpg" alt="">
		</div>
		<div class="info">
			<div class="d-flex align-items-end" v-for="inf in info" :key="inf">

			<ul v-if="inf <= 1">
				{{info.data[0].show.summary}}
<!-- 				<h3 class="show-name"><b>{{ inf.name }}</b></h3>
				<p>Summary: {{ info.data[0].show.summary }}</p>
				<p>Language: {{ info.data[0].show.language }}</p>
				<p>Runtime: {{ info.data[0].show.runtime }}</p>
				<p>premiered: {{ info.data[0].show.premiered }}</p>
				<p>officialSite: {{ info.data[0].show.officialSite }}</p>
				<p>rating: {{ info.data[0].show.rating }}</p> -->
			
			</ul>
			</div>
		</div>
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
      .get('https://api.tvmaze.com/search/shows?q=batman')
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
		border-radius: 20px;
		font-size: 20px;
		color: rgba(0,0,0,0.87);
		text-align: left;
		font-family: Roboto-Medium;
		background: #D6D8E7;
	}
	.img {

		border-radius: 25px;
		height: 300px;
		width: 200px;
		opacity: 0.7;
		padding: 10px;
		object-fit: fill;
	}
	.row>* {
		width: 30%;
	}
	.info p{
		font-family: Roboto-Medium;
		font-size: 12px;
		color: rgba(0,0,0,0.87);
		text-align: left;
	}
	ul {
		font-size: 12px;
	}
</style>