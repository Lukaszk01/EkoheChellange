<template>
  <article class="series-card" :class="{ 'is-favorite': isFavorite }">
    <router-link class="series-card-link" :to="showUrl">
      <div class="container">
        <div class="single-show">
          <div class="row">
            <div class="image">
              <img class="series-card-poster" :src="showImage" :alt="item.show.name" />
            </div>
            <div class="container">
              <div class="row">
                <div class="info">
                    <header class="series-card-header">
                      <h2 class="series-card-title">{{ item.show.name }}</h2>
                        <div class="series-genres">
                          <div
                            class="series-genres-item"
                            v-for="genre in item.show.genres"
                            :key="genre"
                            >
                            <div>{{ genre }}</div>
                        </div>
                      </div>
                  </header> 
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      

      


      
    </router-link>
  </article>
</template>

<script>
import { favoriteStorage } from "../store";
export default {
  props: {
    item: {
      type: Object
    }
  },
  data() {
    return {
      favoriteShows: favoriteStorage.fetch(),
      isFavorite: null
    };
  },
  created() {
    this.setIsFavoriteInitialValue();
  },
  computed: {
    showUrl() {
      return `/show/${this.item.show.id}`;
    },
    showImage() {
      return this.item.show.image
        ? this.item.show.image.medium
        : "images/no-image.png";
    }
  },
  methods: {
    setIsFavoriteInitialValue() {
      this.isFavorite = !!this.favoriteShows[this.item.show.id];
    }
  }
};
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
    margin-bottom: 20px;
  }
  .series-card-poster {
    border-radius: 25px;
    height: 300px;
    width: 200px;
    opacity: 0.7;
    padding: 20px;
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
  .series-card-title {
    text-decoration: none;
  }
</style>