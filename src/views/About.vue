<template>
 


<h2>Main page</h2>




</template>

<script>
// @ is an alias to /src

export default {
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    toggleModal() {
      this.isOpen = !this.isOpen
    }
  }
}
</script>
