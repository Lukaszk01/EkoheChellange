<template>
  <transition name="slide-fade" mode="out-in">
      <router-view />
    </transition>
  <router-view/>
  <footer class="row text-left">
    <p>Terms of Service</p>
    <p>Contact Us</p>
    <i class="fab fa-facebook-f"></i>
    <i class="fab fa-instagram"></i>
    <i class="fab fa-spotify"></i>
    <i class="fab fa-twitter"></i>
    <i class="fab fa-soundcloud"></i>
  </footer>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
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
/*** TRANSITIONS ***/
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
.slide-fade-enter {
  transform: translateX(10px);
  opacity: 0;
}
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.2s ease;
}
.slide-fade-leave-to {
  transform: translateX(-10px);
  opacity: 0;
}
footer {
  height: 40px;
  background: #1A1B35;
  opacity: 0.8;
  font-family: Roboto-Regular;
  font-size: 12px;
  color: rgba(255,255,255,0.87);
  text-align: left;
  opacity: 0.8;
  font-family: Roboto-Regular;
  font-size: 12px;
  color: rgba(255,255,255,0.87);
  text-align: left;
}
</style>
