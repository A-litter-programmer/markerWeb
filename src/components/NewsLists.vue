<template>
  <div class="NewsLists">
    <!-- nav -->
    <div class="nav">
      <div></div>
    </div>
    <!-- left -->
    <div class="centerLeft">
      <el-tabs type="border-card" style="width: 100%; font-size: 10px">
        <el-tab-pane label="图片">
          <ul>
            <li
              v-for="(img, index) in leftList"
              :key="index"
              @click="jumpDetail()"
            >
              {{ img }}
            </li>
          </ul>
        </el-tab-pane>
        <el-tab-pane label="热点">
          <ul>
            <li
              v-for="(img, index) in hotList"
              :key="index"
              @click="jumpDetail()"
            >
              {{ img }}
            </li>
          </ul>
        </el-tab-pane>
      </el-tabs>
    </div>
      <!-- right -->
    <div class="centerRight">
      <div class="userLogin">
        <h5>用户登陆</h5>
      </div>
      <!-- <el-tabs type="border-card" style="width: 100%;font-size:10px;">
        <el-tab-pane label="图片">
          <ul>
            <li v-for="(img,index) in leftList" :key="index" @click="jumpDetail()">{{img}}</li>
          </ul>
        </el-tab-pane>
        <el-tab-pane label="热点">
          <ul>
            <li v-for="(img,index) in hotList" :key="index" @click="jumpDetail()">{{img}}</li>
          </ul>
        </el-tab-pane>
      </el-tabs> -->
      <!-- login -->
      <el-form
        :model="user"
        status-icon
        ref="user"
        label-width="20%"
      >
        <el-form-item label="账号:" prop="userName" style="margin:0px">
          <el-input
            v-model="user.userName"
            autocomplete="off"
            size="mini"
            style="width: 90%;"
          ></el-input>
        </el-form-item>
        <el-form-item label="密码:" prop="passWord" style="margin:0px">
          <el-input
            type="password"
            v-model="user.passWord"
            autocomplete="off"
            size="mini"
            style="width: 90%;"
          ></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" size="small" style="width: 30%;text-align:center " >提交</el-button>
          <el-button size="small" style="width: 30%;text-align:center" @click="resetUser('user')">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
    <!-- center -->
    <div class="hotImages">
      <el-tabs type="border-card" style="width: 50%; font-size: 10px">
        <el-tab-pane label="图片">
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
        <el-tab-pane label="热点">
          <ul>
            <li
              v-for="(img, index) in hotList"
              :key="index"
              @click="jumpDetail()"
            >
              {{ img }}
            </li>
          </ul>
        </el-tab-pane>
      </el-tabs>
      <el-tabs type="border-card" style="width: 50%; font-size: 10px">
        <el-tab-pane label="图片">
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
        <el-tab-pane label="热点">
          <ul>
            <li
              v-for="(img, index) in hotList"
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
      <el-tabs type="border-card" style="width: 50%; font-size: 10px">
        <el-tab-pane label="图片">
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
        <el-tab-pane label="热点">
          <ul>
            <li
              v-for="(img, index) in hotList"
              :key="index"
              @click="jumpDetail()"
            >
              {{ img }}
            </li>
          </ul>
        </el-tab-pane>
      </el-tabs>
      <el-tabs type="border-card" style="width: 50%; font-size: 10px">
        <el-tab-pane label="图片">
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
        <el-tab-pane label="热点">
          <ul>
            <li
              v-for="(img, index) in hotList"
              :key="index"
              @click="jumpDetail()"
            >
              {{ img }}
            </li>
          </ul>
        </el-tab-pane>
      </el-tabs>
    </div>
    <!-- todayworker -->
     <div class="todayWorker">
      <el-table
    :data="tableData"
    border
    style="width: 20%;font-size:10px">
    <el-table-column
      prop="date"
      label="职务"
      width="70%">
    </el-table-column>
    <el-table-column
      prop="name"
      label="姓名"
      width="70%">
    </el-table-column>
    <el-table-column
      prop="number"
      label="联系电话">
    </el-table-column>
  </el-table>

    </div>
    <!-- ------------------------------------- -->
    <!-- <div class="NewsLists1">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>卡片名称</span>
        </div>
        <div v-for="o in 4" :key="o" class="text item" @click="jumpDetail()">{{'列表内容 ' + o }}</div>
      </el-card>
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>卡片名称</span>
        </div>
        <div v-for="o in 4" :key="o" class="text item" @click="jumpDetail()">{{'列表内容 ' + o }}</div>
      </el-card>
    </div>
    <div class="NewsLists1">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>卡片名称</span>
        </div>
        <div v-for="o in 4" :key="o" class="text item" @click="jumpDetail()">{{'列表内容 ' + o }}</div>
      </el-card>
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>卡片名称</span>
        </div>
        <div v-for="o in 4" :key="o" class="text item" @click="jumpDetail()">{{'列表内容 ' + o }}</div>
      </el-card>
    </div>-->
  </div>
</template>

<script>
export default {
  name: "NewsLists",
  data() {
    return {
      leftList: [
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
      ],
      imgList: [
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
        "福建厦门鼓浪屿景区消杀迎开园",
      ],
      hotList: [
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
        "国庆电影票房十大城市：成都反超广州 西安跻身前十",
      ],
      tableData: [ {
          date: '值班员',
          name: '王小虎',
          number: '4654459456'
        },{
          date: '值班员',
          name: '王小虎',
          number: '4654459456'
        },{
          date: '值班员',
          name: '王小虎',
          number: '4654459456'
        }],
      user: {
        userName: "admin",
        passWord: "admin123",
        token: "",
      },
      
      activeName: "second",
    };
  },
  methods: {
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
      }
  },
};
</script>

<style scoped>
.nav {
  width: 100%;
  height: 120px;
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
.centerLeft {
  width: 20%;
  float: left;
  background-color: #409eff;
}
.hotImages {
  display: flex;
  width: 60%;
  /* margin-top: 20px; */
  float: left;
}
.centerRight {
  width: 20%;
  height: 170px;
  float: right;
  background-color: #f5f5f5;
}
.userLogin {
  width: 100%;
}
.userLogin h5 {
  margin: 10px;
  letter-spacing: 10px;
}
/* ---------todayworker----------- */
.todayWorker{
  width: 100%;
  height: 200px;
}
</style>