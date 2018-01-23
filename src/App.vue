<template>
  <div>
    <ul class="mui-table-view mui-grid-view mui-grid-9">

      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-email">
            <span class="mui-badge"></span>
          </span>
          <div class="mui-media-body">一等奖</div>
        </a>
      </li>

      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-email">
            <span class="mui-badge"></span>
          </span>
          <div class="mui-media-body">二等奖</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-chatbubble"></span>
          <div class="mui-media-body">三等奖</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-location"></span>
          <div class="mui-media-body">四等奖</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-search"></span>
          <div class="mui-media-body">五等奖</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-phone"></span>
          <div class="mui-media-body">六等奖</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-gear"></span>
          <div class="mui-media-body">七等奖</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-info"></span>
          <div class="mui-media-body">八等奖</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-more"></span>
          <div class="mui-media-body">九等奖</div>
        </a>
      </li>
    </ul>
    <div class="but">
      <button @click="getbut" style=" background: yellowgreen">点击抽奖</button>
    </div>

    <div class="mui-popup mui-popup-in">
      <div class="mui-popup-inner">
        <div class="mui-popup-title">恭喜你获得</div>
        <div  class="mui-popup-text"></div>
      </div>
      <div class="mui-popup-buttons">
        <span @click="qd" class="mui-popup-button mui-popup-button-bold">确定</span>
      </div>
    </div>
  </div>

</template>

<script>
import $ from "jquery";
export default {
  data() {
    return {
      
    };
  },
 created() {
   
 },
  methods: {
    getbut() {
      var setp = parseInt(Math.random() * 10 + 5);
      var num = 0;
      var len = $("a").length;
      var time = setInterval(function() {
        $("a").removeClass("active");
        $("a")
          .eq([num])
          .addClass("active");
        setp--;
        if (num == len - 1) {
          num = 0;
        } else {
          num++;
        }
    $('.mui-popup-in').css('display','none')
        if (setp == 0) {
          clearTimeout(time);
          var text = $(".active").text();

          var text = $(".active").text();
        
        $('.mui-popup-text').html(text)
        $('.mui-popup').css('display','block')
        }
       
      }, 200);
    },
    qd(){
       $('.mui-popup-in').css('display','none')
    }
  }
};
</script>

<style scoped>
.but {
  display: flex;
  justify-content: center;
}
.active {
  background-color: red;
}
.mui-popup{
  margin: 100px 0;
}
.mui-popup{
display: none;
}
</style>
