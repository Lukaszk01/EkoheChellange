<template>
  <h2>{{msg}}</h2>
<div class="split left">
  <div class="centered">
    <h2>The photo</h2>
    <img class="image" src="@/assets/logInPageImage.svg" alt="">
  </div>
</div>

<div class="split right">
  <div class="centered">
    <div class="container">
      <h1 class="mb-3">Log in</h1>

    <p class="log-inf">Email Address</p>
     <div class="position-relative d-flex flex-row-reverse flex-lg-row flex-wrap flex-lg-nowrap flex-justify-center flex-lg-justify-between pt-6 pb-2 mt-6 f6 text-gray border-top border-gray-light mt-3 mb-3 ml-1"></div>
    <p class="log-inf">Password</p>
    <div class="position-relative d-flex flex-row-reverse flex-lg-row flex-wrap flex-lg-nowrap flex-justify-center flex-lg-justify-between pt-6 pb-2 mt-6 f6 text-gray border-top border-gray-light mt-3 mb-3 ml-1"></div>
      
 

    <div class="container">
      <div class="row text-center">
        <div class="col">
         <div class="checkbox"></div>
          <p class="log-inf">REMEBER ME</p>
          <p class="thin-text">Forgot Password</p>
      </div>
    </div>
    </div>





    
    
    <div class="row d-flex justify-content-between">
      <div class="button-cancel text-center">CANCEL</div>
      <div class="button-login"><router-link class="link" to="/main">LogIn</router-link></div>
    </div>


<div class="container px-4">
  <div class="row gx-5">
    <div class="col">
     <div class="thin-text p-3">Don't have account yet?</div>
    </div>
    <div class="col">
      <div class="thin-text p-3">Sign Up here</div>
    </div>
  </div>
</div>
   
    </div>
  </div>
</div>
    
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


.split {
  height: 100%;
  width: 50%;
  position: fixed;
  z-index: 1;
  top: 0;
  overflow-x: hidden;
  padding-top: 20px;
}


.right {
  right: 0;
  background-color: #ffff;
}

.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}
.centered img {
  width: 1120px;
}
.button-cancel {
  width: 100px;
  height: 30px;
  background: #1A1B35;
  border-radius: 100px;
  font-family: Roboto-Medium;
  font-size: 12px;
  color: #FFFFFF;
  text-align: center;

}
.button-login {
  width: 100px;
  height: 30px;
  background-image: linear-gradient(132deg, #62419A 0%, #3E76EB 100%);
  border-radius: 100px;
  font-family: Roboto-Medium;
  font-size: 12px;
  color: #FFFFFF;
  text-align: center;
}
.checkbox {
  background: #FFFFFF;
  border: 1px solid #CCCCCC;
  border-radius: 2px;
  width: 15px;
  height: 15px;
}
footer {
  height: 50px;
}
.log-inf {
  font-family: Roboto-Medium;
  font-size: 12px;
  color: rgba(0,0,0,0.87);
  text-align: left;
}
.thin-text {
  font-family: Roboto-Light;
  font-size: 12px;
  color: rgba(0,0,0,0.87);
  text-align: right;
}
.link {
  color: #fff;
  text-decoration: none;
}
/*transition animation*/

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
</style>
