<template>
<!--   <div>
    <form @submit.prevent="emitQuery">
      <label for="search-form__input">Pick a TV show you like!</label>
      <input
        id="search-form__input"
        type="search"
        autocomplete="off"
        v-model="query"
      />
      <button>Search</button>
    </form>
  </div> -->
    <div>
    <button @click="toggleModal">Open</button>

    <transition name="fade">
      <div v-if="isOpen" class="modal">
        <p>
          <button @click="toggleModal">Close</button>
        </p>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
      query: this.getInitialQueryValue()
    };
  },
  watch: {
    $route() {
      this.query = this.getInitialQueryValue()
    }
  },
  methods: {
    getInitialQueryValue() {
      return this.$route.query.search || "";
    },
    emitQuery() {
      this.$emit("submit:query", this.query);
    },
    toggleModal() {
      this.isOpen = !this.isOpen
    }
  }
};
</script>

  <style>
  .fade-enter {
    opacity: 0;
  }
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.5s ease-out;
  }
  .fade-leave-to {
    opacity: 0;
  }
  .modal {
    width: 250px;
    height: 200px;
    padding: 10px;
    margin: 0 auto;
    margin-top: 20px;
    border-radius: 2%;
    background-color: #e0e0e0;
}
</style>