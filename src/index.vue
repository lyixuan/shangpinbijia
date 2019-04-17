<template>
  <div class="wrapper">
    <text class="greeting">The environment is ready!</text>
    <HomeList/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import HomeList from './components/HomeList';
import api from './service/base';
import {showapi_appid,showapi_sign} from './config';


export default {
  components: {
    HelloWorld,
    HomeList
  },
  data() {
    return {
      systemParam: {
        showapi_appid,
        showapi_sign
      }
    };
  },
  created() {
  },
  mounted() {
    this.dataLoad();
  },
  methods: {
    dataLoad() {
      const params = {
        keyWords:'洗衣机'
      };
      api.getShopList({...this.systemParam,...params}).then((resp) => {
        console.log(12,resp)
      });
    },
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
