<template>
<div class="split left">
  <div class="centered">
    <!-- <img class="planet" src="@/assets/planetIcon.svg" alt=""> -->
    <img class="image" src="@/assets/logInPageImage.svg" alt="">
    <div class="logo">LOGO</div>
  </div>
</div>

<div class="split right col-12">
  <div class="centered">
    <div class="container">
      <h1>Log in</h1>
        <p class="log-inf">Email Address</p>
          <div class="position-relative d-flex flex-row-reverse flex-lg-row flex-wrap flex-lg-nowrap flex-justify-center flex-lg-justify-between pt-6 pb-2 mt-6 f6 text-gray border-top border-gray-light mt-3 mb-3 ml-1"></div>
        <p class="log-inf">Password</p>
          <div class="position-relative d-flex flex-row-reverse flex-lg-row flex-wrap flex-lg-nowrap flex-justify-center flex-lg-justify-between pt-6 pb-2 mt-6 f6 text-gray border-top border-gray-light mt-3 mb-3 ml-1"></div>
    </div>
  <div class="container">
    <div class="row text-center">
        <div class="col">
          <div class="d-flex justify-content-between">
            <div class="d-flex justify-content-start">
              <div class="checkbox"></div>
              <p class="log-inf ml-3">REMEBER ME</p>
            </div>
          <p class="forgot-password justify-content-end">Forgot Password</p>
        </div>
      </div>
    </div>
    </div>
      <div class="container">
        <div class="row text-center">
          <div class="col">
            <div class="d-flex justify-content-between">
              <div class="button-cancel text-center mt-3">CANCEL</div>
              <div class="button-login mt-3"><router-link class="link" to="/main">LOGIN</router-link></div>
            </div>
          </div>
        </div>
      </div>
      <div class="container">
        <div class="row text-center">
          <div class="col">
            <div class="d-flex justify-content-end">
              <div class="thin-text p-3">Don't have account yet?</div>
              <div class="sign-up p-3">Sign Up here</div>
            </div>
          </div>
        </div>
      </div>
     <!--  <img class="planet" src="@/assets/planetIcon.svg" alt=""> -->
  </div>
</div>
    <footer></footer>
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
  top: 0;
  /*padding-top: 20px;*/
  overflow: hidden;
}


.right {
  right: 0;
  background-color: #ffff;
  display: flex;
}

.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}
.centered img {
  width: 1130px;
  opacity: 0.4;
  z-index: 2;
  position: absolute;
  top: -310px;
  left: -334px;
  display: flex;
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
  padding: 5px;

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
  padding: 5px;
}
.checkbox {
  background: #FFFFFF;
  border: 1px solid #CCCCCC;
  border-radius: 2px;
  width: 15px;
  height: 15px;
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
.container {
  width: 500px;
}
.forgot-password {
  font-family: Roboto-Light;
  font-size: 12px;
  color: rgba(0,0,0,0.87);
  text-align: left;
  text-decoration: underline;
}
.sign-up {
  font-family: Roboto-Light;
  font-size: 12px;
  color: rgba(0,0,0,0.87);
  text-align: right;
  text-decoration: underline;
}
.link {
  font-family: Roboto-Medium;
  font-size: 12px;
  color: #FFFFFF;
  text-align: center;
  padding: 5px;
}
h1 {
  font-family: Roboto-Medium;
  font-size: 20px;
  color: rgba(0,0,0,0.87);
  text-align: center;
  margin-bottom: 50px;
}
.planet {
  position: absolute;
  overflow: hidden;

}
.logo {
  padding: 23px;
  background: #1A1B35;
  border-radius: 13px;
  font-family: Roboto-Medium;
  font-size: 20px;
  color: #FFFFFF;
  text-align: center;
  position: relative;
  border: 1px solid black;
  height: 90px;
  width: 90px;
  text-align: center;
  z-index: 1;
  bottom: 245px;
  opacity: 1;
  right: 270px;
}
/*RESPONSIVE VERSIONS*/
@media only screen and (max-width: 600px) {
  .centered img {
  width: 1130px;
  opacity: 0.4;
  z-index: 2;
  position: absolute;
  top: -310px;
  left: -334px;
  display: none
}
  [class*="col-"] {
    width: 100%;
  }
  .container {
    width: 350px;
  }

}

@media only screen and (min-width: 768px) {
/*  .split {
    width: 100%;
  }
  .container {
    width: 350px;
  }*/
  .centered img {
  width: 1130px;
  opacity: 0.4;
  z-index: 2;
  position: absolute;
  top: -310px;
  left: -334px;
  display: none
}
  [class*="col-"] {
    width: 100%;
  }
}
@media only screen and (min-width: 992px) {
  .centered img {
    display: flex;
  }
  [class*="col-"] {
    width: 50%;
  }
}


</style>
