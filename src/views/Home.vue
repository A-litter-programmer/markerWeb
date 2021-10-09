<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Header />
    <Banner />
    <NewsLists />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Banner from "@/components/Banner.vue";
import NewsLists from "@/components/NewsLists.vue";
export default {
  name: "Home",
  components: {
    // HelloWorld
    Header,
    Banner,
    NewsLists,
  }
};
</script>
<style>
*{
  margin: 0px;
  padding: 0px;
}
</style>
