<template>
  <div class="home">
    <div class="lay" id="lineDrawing">
        <svg width="414" height="341.25" xmlns="http://www.w3.org/2000/svg">
          <g class="lines" fill="none" fill-rule="evenodd" stroke="currentColor" stroke-width="1">
            <path d="M 0 0 H 68.25 V 341.25 H 0 V 0"></path>
            <path d="M 0 136.5 H 273 V 204.75 H 0 V 136.5"></path>
            <path d="M 273 341.25 H 204.75 V 0 H 273 V 341.25"></path>
            <path d="M 373.1 81.9 A 13.65 13.65 90 0 0 373.1 0 A 13.65 13.65 90 0 0 373.1 81.9"></path>
            <path d="M 341.25 95.55 V 341.25 H 409.5 V 95.55 H 341.25"></path>
          </g>
        </svg>
      <div class="message">

        <h1 class="title" id="title">PORTFOLIO</h1>
        <p class="subtitle" id="subtitle">Select the title you want to browse from the list on the left</p>
      </div>
    </div>
  </div>
</template>

<script>
import anime from 'animejs';
export default {
  components: {
  },
  mounted(){
    var lineDrawing = anime({
      targets: '#lineDrawing .lines path',
      strokeDashoffset: [anime.setDashoffset, 0],
      easing: 'easeInOutSine',
      duration: 3000,
      delay: 0,
      direction: 'nomal',
    });
    var message = anime({
      targets: '.title',
      translateY: -20,
      easing: 'easeInOutQuad',
      duration: 1000,
      opacity:1,
    });
    var message = anime({
      targets: '.subtitle',
      translateY: -25,
      easing: 'easeInOutQuad',
      duration: 1000,
      delay:.6,
      opacity:1,
    });
  }
}
</script>
<style scoped>
.home{
  width: 100%;
  height: 100%;
  text-align: center;
  position: relative;
  background-size: cover;
  font-family: Modernist;
  background-color: #202020;
}
.para{
  position:absolute;
  left: 50%;
  top:50%;
  color: black;
  transform: translateX(-50%) translateY(-50%);
  display: flex;

}
.circle{
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border:1px solid black;
}

.lay{
  width: 80%;
  color: white;
  position:absolute;
  left: 50%;
  top:50%;
  color: white;
  transform: translateX(-50%) translateY(-50%);

}
.message{
  text-align: center;
  width: 100%;
}
.title{
  margin:0;
  margin-top:20px;
  font-weight: 900;
  font-size: 70px;
  opacity: 0;
}
.subtitle{
  margin:0;
  font-weight: 100;
  font-size: 20px;
  opacity: 0;
}
path{
  color:white;
}
#lineDrawing{
  position: relative;
}
/* #lineDrawing svg{
  position: absolute;
  top: 50%;
  left: 50%;

  transform: translateX(-50%) translateY(-50%);
} */
</style>
