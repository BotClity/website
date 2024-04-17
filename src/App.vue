<template>
  <div id="menu" class="overlay">
    <div id="logo" @mouseover="onHoverLogo" @mouseleave="onLeaveLogo">
      <img src="./assets/logo/big_logo.png" @click="" class="logo" alt="logo icon" id="logo icon">
    </div>
  </div>
</template>

<script>
import small_logo from  "./assets/logo/small_logo.png"
import big_logo from  "./assets/logo/big_logo.png"
import big_logo_act from "./assets/logo/big_logo_act.png"
import small_logo_act from "./assets/logo/small_logo_act.png"
export default {
  data() {
    return {
      menu: true,
      type_logo: "big"
    };
  },
  methods: {
    onHoverLogo(){
      logo.width = menuWidth * 0.9;
      logo.height= menuHeight * 0.08;
      var logo = document.getElementById("logo icon");
      if (this.type_logo === "big"){
        logo.src = big_logo_act;
      }
      else {
        logo.src = small_logo_act;
      }
    },
    onLeaveLogo(){
      var logo = document.getElementById("logo icon");
      logo.width = menuWidth * 0.8;
      logo.height = menuHeight * 0.07;
      if (this.type_logo === "big"){
        logo.src = big_logo;
      }
      else {
        logo.src = small_logo;
      }
    }
  }
};
window.onload = function (){
  var menuWidth = document.getElementById("menu").offsetWidth;
  var logo = document.getElementById("logo icon");
  var menuHeight = document.getElementById("menu").offsetHeight;
  // Change the logo src based on menu width
  if (menuWidth < 330) {
    logo.src = small_logo;
    this.type_logo = "small";
  } else {
    // Return the default logo src
    logo.src = big_logo;
    this.type_logo = "big";
  }
  logo.width = menuWidth * 0.8;
  logo.height = menuHeight * 0.07;
}
</script>


<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  
}
.overlay {
  background-color: #2e2c2b;
  width: 18%;
  height: 100%;
  left: 0;
  position: fixed;
  top: 0;
  z-index: 1;
  overflow-x: hidden;
  text-align: center;
  padding-top: 20px;
}
.logo{
  position: relative;
}
</style>
