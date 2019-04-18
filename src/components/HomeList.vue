<template>
  <div>
    <list>
      <cell v-for="item in lists">
        <div class="panel">
          <text class="text">aaa</text>
          <text class="text">{{item.shopType}}</text>
        </div>
        <!--<text>{{item.shopTitle}}</text>-->
        <!--<text>{{item.shopPrice}}</text>-->
        <!--<text>{{item.shopImg}}</text>-->
        <!--<a :href="item.shopAddr"}}>-->
          <!--<text>去查看</text>-->
        <!--</a>-->
      </cell>
    </list>
  </div>
</template>

<script>
  import { WxcButton, WxcPopup } from 'weex-ui';
  import {showapi_appid,showapi_sign} from '../config';
  import api from '../service/base';
  const modal = weex.requireModule('modal');
  module.exports = {
    components: { WxcButton, WxcPopup },
    data: () => ({
      systemParam: {
        showapi_appid,
        showapi_sign
      },
      lists: []
    }),
    mounted() {
      this.dataLoad();
    },
    methods: {
      dataLoad() {
        const params = {
          keyWords:'洗衣机'
        };
        console.log(333)
        modal.toast({
          message: '333'
        })
        api.getShopList({...this.systemParam,...params}).then((resp) => {
          console.log(12,12,resp)
          modal.toast({
            message: JSON.stringify(resp.ret_code)
          })
          if (resp.ret_code === 0) {
            this.lists = resp.shopList;
            console.log(this.lists)
          }
        });
      },
    }
  };
</script>
<style scoped>
  .panel {
    width: 600px;
    height: 300px;
    margin-left: 75px;
    margin-top: 35px;
    margin-bottom: 35px;
    flex-direction: column;
    justify-content: center;
    border-width: 2px;
    border-style: solid;
    border-color: rgb(162, 217, 192);
    background-color: rgba(162, 217, 192, 0.2);
  }
  .text {
    font-size: 88px;
    text-align: center;
    color: #41B883;
  }
</style>