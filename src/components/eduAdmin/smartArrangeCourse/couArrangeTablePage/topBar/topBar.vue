<template>
  <div id="couArrangeTable_topBar" class="topBarDiv am-btn-group">
    <button id="topBarButton" class="am-btn am-btn-success" @click="hrefClick(1)">课程设置</button>
    <button class="am-btn am-btn-success" @click="hrefClick(2)">合课设置</button>
    <button class="am-btn am-btn-success btn-active" @click="hrefClick(3)">排课执行</button>
  </div>
</template>

<script>
  export default {
    name: 'couArrangeTable_topBar',
    data () {
      return {
        msg: ''
      }
    },
    mounted: function() {
      try{
        var buttons = document.getElementById("couArrangeTable_topBar").getElementsByTagName("button");
        this.authorityList = JSON.parse(sessionStorage.getItem("authorityList"));
        for (var i = 0; i < buttons.length; i++) {
          buttons[i].style.display = "none";
        }
        for (var i = 0; i < this.authorityList.length; i++) {
          if(this.authorityList[i] == "14"){
            buttons[0].style.display = "block";
          }else if(this.authorityList[i] == "9"){
            buttons[1].style.display = "block";
          }else if(this.authorityList[i] == "7"){
            buttons[2].style.display = "block";
          }
        }
      }catch(e){}
    },
//    权限控制导航显隐
    methods: {
      hrefClick: function (num) {
        if (num == 1) {
          location.href = "#/eduAdmin/course/couArrangeSetting"
        } else if (num == 2) {
          location.href = "#/eduAdmin/course/combineCourse"
        } else if (num == 3) {
          location.href = "#/eduAdmin/course/couArrangeTable"
        }
      }
//      路由跳转
    }
  }
</script>

<style scoped>
  html {
  }
  #couArrangeTable_topBar{

  }
  #topBarButton{
    margin-left: 5rem;
  }
  @media screen and (max-width: 1025px) {
    html {
    }
  }
</style>

