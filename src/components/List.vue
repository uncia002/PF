<template>
  <div class="list">
    <div class="works">
      <div style="margin-bottom:50px;">
        <p class="title">works.</p>
        <div class="work wien" ref="wien">
          <router-link to="wien" class="hover" @click="worksAnimation(0)">
            Wien
          </router-link>
        </div>
        <div class="work modernism" ref="modernism">
          <router-link to="modernism" class="hover" @click="worksAnimation(1)">
            Modernism
          </router-link>
        </div>
        <div class="work aranze" ref="aranze">
          <router-link to="ARANZE" class="hover" @click="worksAnimation(2)">
            Aranze
          </router-link>
        </div>
        <div class="work st" ref="st">
          <router-link to="st" class="hover" @click="worksAnimation(3)">
            Shape
          </router-link>
        </div>
      </div>
    </div>
    <!-- <div class="border">

    </div> -->
  </div>
</template>

<script>
var defa=['wien','modernism','aranze','st']
export default{
  data(){
    return{
      listvalue:['wien','modernism','aranze','st'],
    }
  },
  computed:{
  },
  mounted(){
    this.worksSort()
  },
  methods:{
    worksAnimation(num){
      var transobj = this.$refs[defa[num]]
      transobj.style.top=-30+'px'
      transobj.style.left=210+"px"
      transobj.style.fontWeight='800'
      this.listvalue=new Array('wien','modernism','aranze','st')
      this.listvalue.splice(num,1)
      this.$nextTick(this.worksSort())
      console.log(this.listvalue)
    },
    worksSort(){
      for(let i=0;i<this.listvalue.length;i++){
        var obj=this.$refs[this.listvalue[i]]
        obj.style.top=35*i+10+'px'
        obj.style.left='0'

      }
    },
    worksResets(){
      this.listvalue=new Array('wien','modernism','aranze','st')
      this.worksSort()
    }
  }
}
</script>

<style>

.list{
  position: fixed;
  top: 100px;
  left: 20px;
  z-index: 1;
}
.works{

}
.title{
  margin:0;
  font-weight: 500;
  font-size: 14px;
}
.work{
  margin:0;
  position: absolute;
  transition:.5s;
}
.work a{
  margin:0;
  text-decoration: none;
  font-family: 'Modernist';
  font-size: 36px;
  font-weight: 400;
  position: relative;
  display: inline-block;
}
.work a::after {
  position: absolute;
  bottom: 4px;
  left: 0;
  content: '';
  width: 100%;
  height: 1px;
  background: #DDD;
  transform: scale(0, 1);
  transform-origin: left top;
  transition: transform .3s;
}
.work a:hover::after {
  transform: scale(1, 1);
}
.border{
  position:absolute;
  left:10px;
  top: 30px;
  width:80%;
  height: 70px;
  border:5px solid black;
}

</style>
