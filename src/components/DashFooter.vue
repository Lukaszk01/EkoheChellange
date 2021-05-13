<template>
<footer class="main-footer">
	<div class="row text-left">
		<ul id="fo">
			<li class="term-of-service">Terms of Service</li>
			<li class="contact-us">Contact Us</li>
			<li><img src="@/assets/facebook.svg" alt=""></li>
			<li class="">
				<img src="@/assets/instagram.svg" alt=""></li>
			<li class="">
				<img src="@/assets/tweeter.svg" alt=""></li>
			<li class="">
				<img src="@/assets/soundcloud.svg" alt=""></li>
			<li class="">
				<img src="@/assets/spotify.svg" alt=""></li>
		</ul>  
	</div>
</footer>
</template>

<script>
export default {
  name: 'DashFooter',
  data: function () {
    return {
      year: new Date().getFullYear()
    }
  }
}
</script>
<style>
.main-footer {
  height: 40px;
  background: #1A1B35;
  font-family: Roboto-Regular;
  font-size: 12px;
  color: rgba(255,255,255,0.87);
  text-align: left;
  position: fixed;
  bottom: 0px;
  width: 100%;
}
.main-footer li {
  display: inline-block;
  margin-right: 15px;
  margin-top: 10px;
}
.social-media {
  margin-left: 1120px;
}
.social-media li {
  margin-right: 30px;
  margin-left: 0px;
}
#fo {
  display: inline-block;
}

@media only screen and (max-width: 600px) {
  .main-footer {
    height: 80px;
  }
  li img {
    margin-left: 35px;
    margin-top: 5px;
    margin-bottom: 10px;

  }
  li.contact-us {
    margin-right: 170px;
  }
}
@media only screen and (min-width: 768px) {
  li img {
    margin-right: 8px;
  }
  li.contact-us {
    margin-right: 48%;
  }

}
@media only screen and (min-width: 992px) {
  li.contact-us {
  margin-right: 69%;
}
}

</style>