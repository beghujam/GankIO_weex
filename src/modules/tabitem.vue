<template>
  <div
    :style="{ backgroundColor: backgroundColor }"
    class="container"
    @click="onclickitem">
    <text
      :style="{ color: titleColor }"
      class="tab-text">{{title}}</text>
  </div>  
</template>

<style scoped>
  .container {
    flex: 1; 
    flex-direction: column; 
    align-items:center; 
    justify-content:center; 
    height: 88;
  }
  .top-line {
    position: absolute; 
    top: 0; 
    left: 0; 
    right: 0; 
    height: 2;
  }
  .tab-icon {
    margin-top: 5; 
    width: 40; 
    height: 40
  }
  .tab-text {
    margin-top: 5; 
    text-align: center;  
    font-size: 32;
  }
</style>

<script>
  module.exports = {
    props: {
      index: { default: 0 },
      title: { default: '' },
      titleColor: { default: '#000000' },
      backgroundColor: { default: '#13b2ff' }
    },
    methods: {
      onclickitem: function (e) {
        var params = {
          index: this.index
        };
        this.$emit('tabItemOnClick', params);
      }
    }
  }
</script>
