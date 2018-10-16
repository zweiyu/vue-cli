<template>
  <div class="row tab_header users">
      <div class="col-lg-4 col-xs-5 col-md-4 col-sm-4 col-xs-offset-1 col-lg-offset-2 col-md-offset-2 col-sm-offset-2 active1"  >
        <a  href="#home" class="tr1 col-center-block"  @click="qh(true)" :class="flag==true?'turn1':'turn'" data-toggle="tab">学/工号登录</a>
        <div class="line1 col-lg-offset-3 col-md-offset-2 col-xs-offset-1" :class="flag==true?'ch1':'ch2'" ></div>
      </div>
      <div class="col-lg-3 col-xs-4 col-md-4 col-sm-4 col-lg-offset-1 col-md-offset-1 col-xs-offset-1 active2">
        <a href="#ios" class="tr2" @click="qh(false)" :class="flag==false?'turn2':'turn'" data-toggle="tab">邮箱登录</a>
        <div class="line2" :class="flag==false?'ch1':'ch2'"></div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'users',
  data () {
    return {
      flag:true,
    }
  },

  methods: {
      qh(a)
      {
       this.flag=a;
      }
    }
}
</script>


<style scoped>
@media only screen and (min-width: 320px){
    html {
        font-size:10px !important;
    }
}
@media only screen and (min-width: 360px){
    html {
        font-size:11.25px !important;
    }
}
@media only screen and (min-width: 400px){
    html {
        font-size:12.5px !important;
    }
}
@media only screen and (min-width: 480px){
    html {
        font-size:15px !important;
    }
}
@media only screen and (min-width: 640px){
    html {
        font-size:20px !important;
    }
}

.tab .tab_header{ margin-top:2.7rem;}
.tab .tab_header a{font-size: 1.6rem;text-decoration:none;display: table;margin: auto;}
.tab .tr1:hover{color: #ea8542;}
.tab .tr2:hover{color:#18c869;}

.tab .line1{width: 10rem; height: 0.2rem; background:#ea8542; border-radius:0.25rem; margin-top: 1rem; box-shadow: 0.2rem 0.2rem 0.2rem #e6e6e6;}
.tab .line2{width: 10rem; height: 0.2rem; background: #18c869; border-radius: 0.25rem; margin-top: 1rem; box-shadow: 0.2rem 0.2rem 0.2rem #e6e6e6;}

.turn1 {color:#ea8542;}
.turn2 {color:#18c869;}
.turn{color:#333;}

.ch1{display: block;}
.ch2{display:none;}
</style>
