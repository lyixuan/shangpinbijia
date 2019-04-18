<template>
  <div class="wrapper">
    <div class="demo demo1">
      <text class="value-text">带有目的地模式的输入框</text>
      <wxc-searchbar disabled="true"
                     placeholder="搜索目的地"
                     mod="hasDep"
                     dep-name="杭州出发"
                     @wxcSearchbarDepChooseClicked="wxcSearchbarDepChooseClicked"
                     @wxcSearchbarInputDisabledClicked="wxcSearchbarInputDisabledClicked"></wxc-searchbar>
    </div>
    <HomeList/>
    <!--<Test/>-->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import HomeList from './components/HomeList';
import Test from './components/Test';
import { WxcSearchbar } from 'weex-ui';

export default {
  components: {
    HelloWorld,
    Test,
    HomeList
  },
  data() {
    return {
    };
  },
  created() {
    console.log(11111)
  },
  mounted() {
  },
  methods: {
    wxcSearchbarInputDisabledClicked () {
    },
    wxcSearchbarDepChooseClicked () {
    }
  }
};
</script>

<style scoped>
  .wrapper {
    justify-content: center;
    align-items: center;
  }
  .logo {
    width: 424px;
    height: 200px;
  }
  .greeting {
    text-align: center;
    margin-top: 70px;
    font-size: 50px;
    color: #41B883;
  }
  .message {
    margin: 30px;
    font-size: 32px;
    color: #727272;
  }
</style>
