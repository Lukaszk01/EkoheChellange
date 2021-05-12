<template>
	<div >
    <Search @submit:query="fetchData" />
    <div v-if="$route.query.search" class="series-listing">
      <SearchResult
        v-for="item in showsData"
        :item="item"
        :key="item.show.id"
      />
    </div>
  </div>
<!--   <h2>Main page</h2>
<i class="fab fa-facebook-f"></i>
<div class="container">
	<div class="single-show">
		<div class="row">
			<div class="image">
				<img class="img" src="https://static.tvmaze.com/uploads/images/original_untouched/31/78286.jpg" alt="">
			</div>
			<div class="container">
				<div class="row">
					<div class="info" v-for="inf in info" :key="inf">
						<div v-if="inf >= 1">
							<p>{{info.data[0].show.summary}}</p> 
						</div>
						<div v-else-if="inf.length > 1">
							
						</div>
					</div>
				</div>
			</div>
			</div>
		</div>	
	</div> -->










		<!--<h3 class="show-name"><b>{{ inf.name }}</b></h3>
								<p>Summary: {{ info.data[0].show.summary }}</p>
								<p>Language: {{ info.data[0].show.language }}</p>
								<p>Runtime: {{ info.data[0].show.runtime }}</p>
								<p>premiered: {{ info.data[0].show.premiered }}</p>
								<p>officialSite: {{ info.data[0].show.officialSite }}</p>
								<p>rating: {{ info.data[0].show.rating }}</p> -->
</template>

<script>
import axios from "axios";
import Search from "../components/Search";
import SearchResult from "../components/SearchResult";
export default {
  components: {
    Search,
    SearchResult
  },
  data() {
    return {
      showsData: []
    };
  },
  created() {
    this.fetchDataFromQuery();
  },
  watch: {
    $route() {
      this.fetchDataFromQuery();
    }
  },
  methods: {
    async fetchData(showsQuery) {
      try {
        const response = await axios.get(
          `http://api.tvmaze.com/search/shows?q=${showsQuery}`
        );
        this.setUrlQuery(showsQuery);
        this.showsData = response.data;
      } catch (err) {
        console.error(err.message);
      }
    },
    setUrlQuery(searchQuery) {
      if (this.$route.query.search !== searchQuery) {
        this.$router.push({
          name: "Main",
          query: {
            search: searchQuery
          }
        });
      }
    },
    fetchDataFromQuery() {
      const search = this.$route.query.search;
      if (search && search !== "") {
        this.fetchData(search);
      }
    }
  }
};
// import axios from 'axios'


// export default {
//   data() {
//     return {
//       info: null,
//       isOpen: false
//     }
//   },
//   methods: {
//     toggleModal() {
//       this.isOpen = !this.isOpen
//     }
//   },
//   mounted () {
//     axios
//       .get('https://api.tvmaze.com/search/shows?q=batman')
//       // You can change the link above to your API
//       // Note: I've found it sometimes only works with HTTPS
//       .then(response => (this.info = response))
//   }
// }
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
		margin: 0px;
	}
	.row>* {
		width: 30%;
		margin-left: 0px;
	}
	.info p {
		font-family: Roboto-Medium;
		font-size: 12px;
		color: rgba(0,0,0,0.87);
		text-align: left;
		margin: 50px;
		width: 800px;
	}
	ul {
		font-size: 12px;
	}
	.series-listing {
		margin: 100px;
	}
	#search-form__input {
		margin-top: 50px;
		border-radius: 10px;
		border: 1px solid gray;
		margin-left: 10px;
		box-shadow: 0.5px 0.5px 2px gray;
		height: 30px;
		width: 200px;
		font-size: 20px;
	}
	
/*	#search-form__input:hover {
		background-color: #f2efef;
		border: 1px solid gray;
		box-shadow: 3px 3px 10px #1A1B35;
	}*/
	button {
		border-radius: 10px;
		border: 1px solid gray;
		margin: 5px;
		box-shadow: 0.5px 0.5px 2px gray;
		background-color: #1A1B35;
		color: #FFFF;
		font-family: Roboto-Medium;
	}
	button:hover {
		color: #1A1B35;
	}
</style>