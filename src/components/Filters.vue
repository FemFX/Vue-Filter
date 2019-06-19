<template>
  <div class="hello">
    <div class="white"></div>
    <img src="https://avatars.mds.yandex.net/get-pdb/70729/5f92a806-a452-45d4-ad56-83f9b4cc4229/s1200?webp=false" class="img">
    <div class="menu">
      <h1>Settings</h1>
      <br>
      <div class="settingVal">Blur :</div><input type="range" class="blur" min="0" max="5" @change='this.blurChange' value='0'> 
      <div class="settingVal">Alpha :</div><input type="range" class="wawe" min="1" max="10" @change='this.waweChange' value='0'> 
       <div class="settingVal">White :</div><input type="range" class="wawe" min="1" max="10" @change='this.whiteChange' value='0'> 
    </div>
  </div>
</template>

<script>

export default {
  name: 'Filters',
  data() {
    return {
      blur : 0,
      opacity : 1,
      opacityWhite : 0
    }
  },
  methods: {
    blurChange(event){
      const img = document.querySelector('img'); 
      console.log(event.target.value);
      this.blur = event.target.value
      img.style.filter = `blur(${this.blur}px)`
  },
  waweChange(event){
      const img = document.querySelector('img'); 
      console.log(event.target.value);
      this.opacity = event.target.value
      img.style.opacity = `0.${this.opacity}`
  },
  whiteChange(event){
    const white = document.querySelector('.white'); 
      console.log(event.target.value);
      this.opacityWhite = event.target.value
      white.style.opacity = `0.${this.opacityWhite}`
  }
  },
  
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body{
  margin: 0;
  padding: 0;
}
.white{
  position: absolute;
  right: 0;
  top: 0;
  height: 100%;
  width: 81%;
  background: #fff;
  z-index: 999;
  opacity: 0;
}
img{
  position: absolute;
  right: 0;
  top: 0;
  height: 100%;
  width: 85%;
}
.menu{
    position: absolute;
    left: 0;
    top: 0;
    width: 250px;
    height: 100vh;
    background: #2d3436;
    color: #fff;
}
.settingVal{
  position: relative;
  left: -100px;
}
input{

  width: 90%;
}
</style>
