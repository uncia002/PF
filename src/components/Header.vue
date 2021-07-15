<template>
  <div class="header">
    <div class="hover">
      <router-link style="font-weight:700;font-size:23px;" to="/" class="hover" @click="worksResets()">
        NIWASAKI ITSU
      </router-link>
    </div>
    <div style="margin-left:30px;" class="hover about">
      <router-link to="whoami" class="hover" @click="worksResets()">
        ABOUT
      </router-link>
    </div>
    <div style="margin-left:30px;" class="hover about">
      <a href="https://github.com/uncia002/portfolio" target="_blank" rel="noopener noreferrer">GITHUB</a>
    </div>
  </div>
</template>

<script>

export default{
  data(){
    return{

    }
  },
  methods:{
    worksResets(){
      this.$emit('reset');
      console.log("agasa")
    }
  },
  computed:{
  }
}
</script>

<style>

.header{
  position: fixed;
  top: 20px;
  left: 20px;
  color: #DDD;
  display: flex;
}
a{
  margin:0;
  text-decoration: none;
  color:#DDD;
}
.about{
  font-weight:500;
  font-size:13px;
  vertical-align:bottom;
  line-height: 26px;
}
</style>
