<template>
  <div class="news">
    <div class="news-box" >
      <loading v-show="msg.state==0"></loading>
      <div class="news-content-box" v-for="item in msg.list" :key="item.id" v-show="msg.state==1">
        <div class="item">
          <router-link :to="'/newsDetails/' + item.id" >
            <div class="item-title">{{item.title}}</div>
          </router-link>
          <div class="item-time">【{{item.time.split(" ")[0]}}】</div>
        </div>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  name: "indexlaws",
  props:['msg'],
  data() {
    return {

    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.news{
    .news-box{width: 100%;
        .news-content-box{width: 100%;margin-top: 20px;margin-bottom: 20px;
            &:hover{cursor: pointer;}
            .item{position: relative; width: 100%;display: flex;justify-content:space-between;margin-bottom: 15px;box-sizing: border-box;padding:0 5px 0 12px;align-items: center;
                .item-title{width: 270px;font-size: 16px;color: #3d3d3d;font-weight: 500;overflow: hidden;text-overflow: ellipsis;white-space: nowrap;}
                .item-time{font-size: 12px;color: #3d3d3d;}
                
            }
            .item:before{content: "";width: 6px;height: 6px;border-radius: 6px;background-color: #952418;position: absolute;left: 0px;top:50%;display: block;margin-top: -3px;}
            .item:hover{
                div{color:#952418;}
                &:before{background-color:#952418;}
            }
            
        }
       
    }
} 

</style>
