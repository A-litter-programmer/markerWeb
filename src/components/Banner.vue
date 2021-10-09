<template>
  <div class="banner">
    <div class="item">
      <img :src="dataList[currentIndex]" @click="jumpDetail()" />
    </div>
    <div class="page" v-if="this.dataList.length > 1">
      <ul>
        <!-- <li @click="gotoPage(prevIndex)">&lt;</li> -->
        <li
          v-for="(item,index) in dataList"
          :class="{'current':currentIndex == index}"
          class="point"
          :key="index"
        ></li>
        <!-- <li @click="gotoPage(nextIndex)">&gt;</li> -->
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
  data() {
    return {
      dataList: [
        "https://i1.mifile.cn/a4/xmad_15535933141925_ulkYv.jpg",
        "https://i1.mifile.cn/a4/xmad_15532384207972_iJXSx.jpg",
        "https://i1.mifile.cn/a4/xmad_15517939170939_oiXCK.jpg"
      ],
      currentIndex: 0, //默认显示图片
      timer: null //定时器
    };
  },
  computed: {
    //上一张
    prevIndex() {
      if (this.currentIndex == 0) {
        return this.dataList.length - 1;
      } else {
        return this.currentIndex - 1;
      }
    },
    //下一张
    nextIndex() {
      if (this.currentIndex == this.dataList.length - 1) {
        return 0;
      } else {
        return this.currentIndex + 1;
      }
    }
  },
  mounted() {
    this.runInv(); // 初始的时候加载
  },
  methods: {
    jumpDetail() {
      this.$router.push("/detail");
    },
    gotoPage(index) {
      this.currentIndex = index;
    },
    //定时器
    runInv() {
      this.timer = setInterval(() => {
        this.gotoPage(this.nextIndex);
      }, 5000);
    }
  }
};
</script>

<style scoped>
ul li {
  list-style: none;
  float: left;
  /* width: 30px;
  height: 40px; */
  /* line-height: 40px; */
  text-align: center;
  cursor: pointer;
  color: rgba(255, 255, 255, 0.8);
  font-size: 14px;
}
.banner {
  width: 90%;
  margin: 0 auto;
  position: relative;
}
.banner .item {
  margin-top: 120px;
}
.banner img {
  width: 100%;
  height: 120px;
  display: block;
}
.banner .page {
  position: absolute;
  right: 50%;
  bottom: 0;
  width: 100%;
}
.banner .page ul {
  float: right;
}
.point {
  width: 5px;
  height: 5px;
  margin-right: 5px;
  background-color: #fff;
  border-radius: 50%;
}
.current {
  background-color: #409eff;
}
</style>