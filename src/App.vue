<template>
  <div class="main">
    <List ref="List" />
    <Header @reset="worksResets"/>
    <div class="router">
      <router-view v-slot="{ Component }">
        <transition appear>
          <component :is="Component" />
        </transition>
      </router-view>
    </div>
    <div id="stalker" class="agas">

    </div>
  </div>
</template>

<script>
import List from '@/components/List.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'App',
  components: {
    List,
    Header,
  },
  data(){
    return{
      isActive:false,

    }
  },
  methods:{
    worksResets(){
      this.$refs.List.worksResets()
      console.log("sdfsdfsd")
    },
  },
  mounted(){
    //マウスストーカー用のdivを取得
    const stalker = document.getElementById('stalker');

    //aタグにホバー中かどうかの判別フラグ
    let hovFlag = false;

    //マウスに追従させる処理 （リンクに吸い付いてる時は除外する）
    document.addEventListener('mousemove', function (e) {
      if (!hovFlag) {
      stalker.style.transform = 'translate(' + e.clientX + 'px, ' + e.clientY + 'px)';
      }
    });

    //リンクへ吸い付く処理
    const linkElem = document.querySelectorAll('a:not(.no_stick_)');
    for (let i = 0; i < linkElem.length; i++) {
      //マウスホバー時
      linkElem[i].addEventListener('mouseover', function (e) {
        hovFlag = true;

        //マウスストーカーにクラスをつける
        stalker.classList.add('hov');

        //マウスストーカーの位置をリンクの中心に固定
        let rect = e.target.getBoundingClientRect();
        let posX = rect.left + (rect.width / 2);
        let posY = rect.top + (rect.height / 2);

        stalker.style.transform = 'translate(' + posX + 'px, ' + posY + 'px)';

      });
      //マウスホバー解除時
      linkElem[i].addEventListener('mouseout', function (e) {
        hovFlag = false;
        stalker.classList.remove('hov');
      });
    }
  }
}
</script>

<style>
@font-face {
  font-family: "Modernist";
  src: url("./assets/Modernist.otf");
}
@font-face {
  font-family: "Morganite";
  src: url("./assets/Morganite-Bold.ttf");
}
@font-face {
  font-family: "MorganiteLight";
  src: url("./assets/Morganite-Thin.ttf");
}
@font-face {
  font-family: "BebasNeue";
  src: url("./assets/BebasNeue.ttf");
}
::-webkit-scrollbar {
    width: 2px;
}

/*スクロールバーの軌道*/
::-webkit-scrollbar-track {
  /* border-radius: 2px;
  box-shadow: inset 0 0 4px rgba(0, 0, 0, .1); */
}

/*スクロールバーの動く部分*/
::-webkit-scrollbar-thumb {
  background-color: #555;
  border-radius: 2px;
}
*{
}
html{
  width: 100%;
  height: 100%;
}
body{
  margin:0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  width: 100%;
  height: 100%;
  background-color:#202020;
  color:#DDD;
}
.main{
  width: 100%;
  height: 100%;
  display: flex;
}



.router{
  width: calc(100% - 240px);
  height: calc(100% - 140px);
  position: absolute;
  top:120px;
  left: 220px;
  /* border:1px solid white; */
  overflow: auto;
  overflow-x: hidden
}
.agas {
  pointer-events: none;
  position: fixed;
  top: -8px;
  left: -8px;
  width: 16px;
  height: 16px;
  background: rgba(0,0,0,0.5);
  border-radius: 50%;
  transition: transform 0.2s, top, 0.5s, left 0.5s, width .5s, height .5s, background-color .5s;
  transition-timing-function: ease-out;
  z-index: 999;

}
.hov{
  top: -32px;
  left: -32px;
  width: 64px;
  height: 64px;
  transition: 0.5s;
  background: rgba(255, 0, 0, 0.4);
}

.v-enter {
  transform: translate(-100px, 0);
  opacity: 0;
}
.v-enter-to {
  opacity: 1;
}
.v-enter-active {
  transition: all 1.5s 5s ease;
}
.v-leave {
  transform: translate(0, 0);
  opacity: 1;
}
.v-leave-to {
  transform: translate(50px, 0);
  opacity: 0;
}
.v-leave-active {
  transition: all 1s 0s ease;
}

</style>
