<template>
  <div id="tchTeachingPlanPageTopBar" class="topBarDiv am-btn-group">
    <!--导航栏-->
    <button class="am-btn am-btn-success btn-active" style="margin-left: 5rem">教学计划审批</button>
    <router-link to="/eduAdmin/examination/adjustCouApply"><button class="am-btn am-btn-success">调课审批</button></router-link>
    <router-link to="/eduAdmin/examination/makeupCouApply"><button class="am-btn am-btn-success">补课审批</button></router-link>
    <router-link to="/eduAdmin/examination/suspendCouApply"><button class="am-btn am-btn-success">停课审批</button></router-link>
    <router-link to="/eduAdmin/examination/banCouApply"><button class="am-btn am-btn-success">禁排审批</button></router-link>
    <router-link to="/eduAdmin/examination/eduAdminEvaTeachingResult"><button class="am-btn am-btn-success">教务查看评教</button></router-link>
    <router-link to="/eduAdmin/examination/makeupExamAdmin"><button class="am-btn am-btn-success">补考审批</button></router-link>
  </div>
</template>

<script>
    export default {
        name: 'tchTeachingPlanPageTopBar',
        data () {
            return {
                msg: ''
            }
        },
      mounted: function(){
        try{
          var buttons = document.getElementById("tchTeachingPlanPageTopBar").getElementsByTagName("button");
          var authorityList = JSON.parse(sessionStorage.getItem("authorityList"));
          for(var i=0;i<buttons.length;i++){
            buttons[i].style.display="none";
          }
          for(var j=0;j<authorityList.length;j++){
            if(this.authorityList[j] == "17"){
              buttons[0].style.display = "block";
            }else if(this.authorityList[j] == "12"){
              buttons[1].style.display = "block";
            }else if(this.authorityList[j] == "13"){
              buttons[2].style.display = "block";
            }else if(this.authorityList[j] == "11"){
              buttons[3].style.display = "block";
            }else if(this.authorityList[j] == "8"){
              buttons[4].style.display = "block";
            }else if(this.authorityList[j] == "62"){
              buttons[5].style.display = "block";
            }else if(this.authorityList[j] == "30"){
              buttons[6].style.display = "block";
            }
          }
        }catch(e){}
      }
    }
</script>

<style scoped>
    html {
        font-size: 100%;
    }

    @media screen and (max-width: 1025px) {
      html {
        font-size: 56%;
      }
    }
    @media screen and (max-width: 1025px) {
      .am-btn-group button{
        width: 13rem;
      }
    }
    @media screen and (min-width: 1025px) and (max-width: 1152px) {
      .am-btn-group button{
        width: 7.7rem;
      }
    }
    @media screen and (min-width: 1152px) and (max-width: 1281px) {
      .am-btn-group button{
        width: 8.8rem;
      }
    }
    @media screen and (min-width: 1281px) and (max-width: 1440px) {
      .am-btn-group button{
        width: 10rem;
      }
    }
</style>
