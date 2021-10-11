<template>
  <div class="NewsLists">
    <!-- nav -->
    <div class="nav">
      <div class="navLeft">
        <h4>“实践教育活动”专题</h4>
      </div>
      <div class="navLeft">
        <h4>学习宣传党的十九大精神</h4>
      </div>
      <div class="navLeft">
        <h4>党史教育</h4>
      </div>
      <div class="navLeft">
        <h4>“两学一做”学习教育专题</h4>
      </div>
    </div>
    <div class="top">
      <!-- left -->
      <div class="centerLeft">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <div class="item">
            <img :src="leftImage[currentIndex]" @click="jumpDetail()" />
          </div>
          <div class="page" v-if="this.leftImage.length > 1">
            <ul>
              <!-- <li @click="gotoPage(prevIndex)">&lt;</li> -->
              <li
                v-for="(item, index) in leftImage"
                :class="{ current: currentIndex == index }"
                class="point"
                :key="index"
              ></li>
              <!-- <li @click="gotoPage(nextIndex)">&gt;</li> -->
            </ul>
          </div>
        </el-tabs>
      </div>
      <!-- topCenter -->
      <div class="recentNews">
        <el-tab-pane label="最新信息">
          <ul>
            <li
              v-for="(news, index) in newsList"
              :key="index"
              @click="jumpDetail()"
            >
              {{ news }}
            </li>
          </ul>
        </el-tab-pane>
      </div>
      <!-- right -->
      <div class="right">
        <div class="rRight">
          <div class="userLogin">
            <h5>用户登陆</h5>
          </div>
          <!-- login -->
          <el-form :model="user" status-icon ref="user" label-width="20%">
            <el-form-item label="账号:" prop="userName" style="margin-top: 10px">
              <el-input
                v-model="user.userName"
                autocomplete="off"
                size="small"
                style="width: 90%"
              ></el-input>
            </el-form-item>
            <el-form-item label="密码:" prop="passWord" style="margin: 0px;font-size:16px">
              <el-input
                type="password"
                v-model="user.passWord"
                autocomplete="off"
                size="small"
                style="width: 90%"
              ></el-input>
            </el-form-item>
            <el-form-item>
              <el-button
                type="primary"
                size="small"
                style="width: 30%; text-align: center"
                >提交</el-button
              >
              <el-button
                size="small"
                style="width: 30%; text-align: center; margin-left: 10px"
                @click="resetUser('user')"
                >重置</el-button
              >
            </el-form-item>
          </el-form>
        </div>
        <!-- todayworker -->
        <div class="todayWorker">
          <div class="onlinePersonnel">
            <h5>今日机关值班人员</h5>
          </div>
          <el-table
            :data="tableData"
            border
            style="width: 100%; font-size: 10px"
          >
            <el-table-column prop="date" label="职务" width="60%">
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="60%">
            </el-table-column>
            <el-table-column prop="number" label="联系电话"> </el-table-column>
          </el-table>
        </div>
      </div>
    </div>
    <!-- center -->
    <div class="center">
      <!-- centerNav -->
      <div class="centerNav">
        <img src="#" alt="404" />
      </div>
      <!-- centerRight -->
      <div class="centerRight">
        <div class="time"></div>
        <h5>
          填写值班记录本<br />查看值班时间安排<br />市场监管局通讯录（注意保密）
        </h5>
        <!------------------------>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
      </div>
      <!-- document -->
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="近期文件">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="市场监管">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="明传电报">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="市场监管红头文件">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
    </div>
    <!-- Service platform -->
    <div class="center">
      <!-- centerNav -->
      <div class="centerNav">
        <img src="#" alt="404" />
      </div>
       <div class="centerRight">
        <div class="subject"></div>
        <!------------------------>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
        <div class="subject">
          <img src="#" />
        </div>
      </div>
      <!-- center -->
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="法律法规">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="纪检监察">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="经验交流">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
      <div class="hotImages">
        <el-tabs type="border-card" style="width: 100%; font-size: 10px">
          <el-tab-pane label="案例分析">
            <ul>
              <li
                v-for="(img, index) in imgList"
                :key="index"
                @click="jumpDetail()"
              >
                {{ img }}
              </li>
            </ul>
          </el-tab-pane>
        </el-tabs>
      </div>
    </div>
    <!-- bottom -->
    <div class="bottom">
      <div class="bottomSwriper">
      </div>
      <div class="footer"></div>
    </div>
  </div>

</template>

<script>
export default {
  name: "NewsLists",
  data() {
    return {
      //centerLeft
      leftImage: [
        "https://i1.mifile.cn/a4/xmad_15535933141925_ulkYv.jpg",
        "https://i1.mifile.cn/a4/xmad_15532384207972_iJXSx.jpg",
        "https://i1.mifile.cn/a4/xmad_15517939170939_oiXCK.jpg",
      ],
      currentIndex: 0, //默认显示图片
      timer: null, //定时器

      // newsList
      newsList: [
        "福建厦门鼓浪屿景园",
        "福建厦门屿景区开园",
        "福建厦门鼓浪屿景区消",
        "福建厦门鼓浪屿景开园",
        "福建厦门鼓浪屿景区开园",
      ],

      imgList: [
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        // "福建厦门鼓浪屿景区消杀迎开园",
        // "福建厦门鼓浪屿景区消杀迎开园",
      ],
      hotList: [
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
      ],
      tableData: [
        {
          date: "值班员",
          name: "王小虎",
          number: "4654459456",
        },
        {
          date: "值班员",
          name: "王小虎",
          number: "4654459456",
        },
        {
          date: "值班员",
          name: "王小虎",
          number: "4654459456",
        },
      ],
      user: {
        userName: "admin",
        passWord: "admin123",
        token: "",
      },

      activeName: "second",
    };
  },
  //图片轮播
  computed: {
    //上一张
    prevIndex() {
      if (this.currentIndex == 0) {
        return this.leftImage.length - 1;
      } else {
        return this.currentIndex - 1;
      }
    },
    //下一张
    nextIndex() {
      if (this.currentIndex == this.leftImage.length - 1) {
        return 0;
      } else {
        return this.currentIndex + 1;
      }
    },
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
    },
    // 跳转到详情页
    jumpDetail() {
      this.$router.push("/detail");
    },
    handleClick(tab, event) {
      console.log(tab, event);
    },
    // ---------提交---------------
    //  submitForm(formName) {
    //     this.$refs[formName].validate((valid) => {
    //       if (valid) {
    //         alert('submit!');
    //       } else {
    //         console.log('error submit!!');
    //         return false;
    //       }
    //     });
    //   },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    },
  },
};
</script>

<style scoped>
.nav {
  width: 100%;
  height: 80px;
}
.navLeft {
  width: 24%;
  height: 100%;
  margin: 0 0.5% ;
  background-image: url("../../public/img/党史.jpeg");
  background-size: 100% 100%;
  float: left;
}
ul {
  list-style: none;
}
ul li {
  cursor: pointer;
  padding: 5px;
}
ul li:hover {
  color: #409eff;
}
.NewsLists {
  width: 90%;
  margin-left: 5%;
  background-color: #fff;
  overflow: hidden;
}
/* -------top---------- */
.top {
  width: 100%;
  height: 400px;
  display: flex;
}
/* ------------------------------ */
.centerLeft {
  width: 30%;
  height: 400px;
  float: left;
  flex-grow: 0;
  flex-shrink: 0;
  background-color: #409eff;
}
.centerLeft img {
  width: 100%;
  height: 220px;
  display: block;
}
/* -----------recentNews----------------- */
.right {
  width: 20%;
  height: 400px;
}
.recentNews {
  width: 50%;
  height: 400px;
  flex-grow: 0;
  flex-shrink: 0;
  background-color: aqua;
}
/* ---------------------------- */
.rRight {
  width: 100%;
  height: 170px;
  flex-grow: 0;
  flex-shrink: 0;
  /* float: right; */
  background-color: #f5f5f5;
}
.userLogin {
  width: 100%;
  height: 20px;
}
.userLogin h5 {
  margin: 10px;
  margin-top: 0px;
  padding-top: 5px;
  letter-spacing: 10px;
  font-size: 20px;
}
/* ---------todayworker----------- */
.todayWorker {
  width: 100%;
  height: 230px;
  flex-grow: 0;
  flex-shrink: 0;
  /* background-color: red; */
}
/* ------------online--------------------- */
.onlinePersonnel {
  width: 100%;
}
.onlinePersonnel h5 {
  /* margin: 10px; */
  padding: 10px 0;
  letter-spacing: 10px;
  background-color: #409eff;
  color: red;
}
/* -----------------center-------------------------*/
.center {
  width: 100%;
  height: 500px;
  overflow: hidden;
  background-color: saddlebrown;
}
/* -------------centerNav----------------- */
.centerNav {
  width: 80%;
  height: 80px;
  float: left;
  background-color: red;
}
.hotImages {
  display: flex;
  width: 40%;
  height: 210px;
  /* margin-top: 20px; */
  float: left;
}
.centerRight {
  width: 20%;
  height: 500px;
  float: right;
  background-color: salmon;
}
.time {
  width: 100%;
  height: 27px;
}
.centerRight h5 {
  color: #065fb8;
  text-align: center;
}
.subject {
  width: 90%;
  height: 62px;
  margin: 6px 12px;
  border-radius: 2%;
  background: chartreuse;
}
</style>