<template>
  <div>
    <list>
      <cell v-for="num in lists">
        <text>{{num}}</text>
      </cell>
    </list>
  </div>
</template>

<script>
  import { WxcButton, WxcPopup } from 'weex-ui';

  module.exports = {
    components: { WxcButton, WxcPopup },
    data: () => ({
      lists: ['A', 'B', 'C', 'D', 'E']
    }),
    methods: {
      buttonClicked () {
        this.isShow = true;
      },
      overlayClicked () {
        this.isShow = false;
      }
    }
  };
</script>
