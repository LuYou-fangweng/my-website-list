<template>
  <div class="home">
    <div class="topImg">
      <div class="topText">
        个人网站作品集
      </div>
    </div>
    <div class="contend">
      <ul class="webList">
        <a
          class="item"
          v-for="(item, index) in dataList"
          :key="index"
          :href="item.path"
        >
         <div class="float"></div>
          <div class="webBox">
            <img :src="item.img" :alt="item.name" class="cover" />
           
          </div>
          <div class="title">{{ item.name }}</div>
        </a>
      </ul>
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
export default {
  name: "Home",
  data() {
    return {
      dataList: [
        {
          name: "绘斓艺馨",
          img: "https://aqbyzdq.oss-cn-guangzhou.aliyuncs.com/website-cover/%E7%BB%98%E6%96%93%E8%89%BA%E9%A6%A8%E8%A7%86%E9%A2%91%E7%BD%91.png",
          path: "https://video-play-seven.vercel.app",
        },
        {
          name: "绘斓艺馨—后台管理",
          img: "https://aqbyzdq.oss-cn-guangzhou.aliyuncs.com/website-cover/%E7%BB%98%E6%96%93%E8%89%BA%E9%A6%A8%E5%90%8E%E5%8F%B0%E7%AE%A1%E7%90%86.png",
          path: "https://backstage-supporter.vercel.app",
        },
        {
          name: "仿原神官网",
          img: "https://aqbyzdq.oss-cn-guangzhou.aliyuncs.com/website-cover/%E4%BB%BF%E5%8E%9F%E7%A5%9E%E5%AE%98%E7%BD%91.png",
          path: "https://genshin-web-theta.vercel.app",
        },
        {
          name: "白鹭音乐播放器",
          img: "https://aqbyzdq.oss-cn-guangzhou.aliyuncs.com/website-cover/%E7%99%BD%E9%B9%AD%E9%9F%B3%E4%B9%90.png",
          path: "https://egretmusics.vercel.app/",
        },
      ],
    };
  },
  components: {},
};
</script>
<style lang="scss" scoped>
.home {
  .topImg {
    width: 100vw;
    position: relative;
    height: 160px;
    background: no-repeat
      url("https://aqbyzdq.oss-cn-guangzhou.aliyuncs.com/background/%E8%93%9D%E8%89%B2%E4%B8%BB%E9%A2%98/VxYQ03poXW.jpg")
      center;
    background-size: cover;
    // object-fit: cover;
    .topText{
      height: 60px;
      width: 100%;
      font: 400 50px/60px 楷体;
      font-style: italic;
      color: rgb(0, 99, 145);
      position: absolute;
      top: 50%;
      left: 0px;
      transform: translate(0,-50%);
    }
  }
  .contend {
    // min-height: 500px;
    background-image: linear-gradient(
      rgba(240, 251, 255, 0.842) 0,
      rgba(250, 250, 250, 0) 400px
    );
    padding-top: 20px;
    .webList {
      box-sizing: border-box;
      padding: 0px;
      margin: 0px auto;
      width: 1080px;
      list-style: none;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;

      .item {
        display: block;
        box-sizing: border-box;
        border: 1px solid #eee;
        border-radius: 4px;
        box-shadow: 2px 2px 10px 3px rgba(0, 0, 0, 0.2);
        position: relative;
        .float {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0px;
            left: 0px;
            background-color: rgba(0, 0, 0, 0.07);
            transition: all 0.3s ease;
          }
          &.item:hover {
            .float{
                background-color: rgba(0, 0, 0, 0);
            }
            .title{
              color: rgb(31, 178, 236);
            }
              
            }
        .webBox {
          line-height: 0px;
          .cover {
            width: 100%;
          }
          
        }
        .title {
          height: 50px;
          font: 400 30px/50px 楷体;
          color: rgb(0, 95, 124);
          text-align: center;
          transition: all 0.3s ease;
        }
      }
    }
  }
  @media screen  and (max-width:900px){
  .contend{
    .webList {
      width:100%;
      display: grid;
      grid-template-columns: 1fr;
      gap: 10px;
      padding: 0px 10px;
}
.float{
  display: none;
}
  }
}
}
</style>
