<template>
  <div class="header">
    <div class="header-container">
      <div class="container">
        <div class="nav">
            <div class="username">
                <router-link :to="{name:'Home'}" style="margin-right:60px ">登录</router-link>
                <router-link :to="{name:'Home'}" style="margin-right:60px ">注册</router-link>
            </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Header",
};
</script>
<style scoped>
.header{
  margin: 0px;
  padding: 0px;
  width: 100%;
  height: 10%;
}
.header-container {
  width: 100%;
  background: #FFFF;
  /* color: #fff; */
  line-height: 30px;
  position: fixed;
  z-index: 100;
  left: 0;
  top: 0;
  /* display: flex; */
}
.nav {
  width: 100%;
  /* margin: auto; */
  flex-grow: 1;
  display: flex;
  justify-content: flex-end;
}
.nav .router-link-exact-active {
  color: #409eff;
  text-decoration: none;
  /* margin-left: 10%; */
}
</style>