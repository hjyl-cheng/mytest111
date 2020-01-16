<template>
  <div>
    <button @click="showOrhide">显示/隐藏</button>
    <input ref="input" v-if="isShow" type="text">
  </div>
</template>
<script>
  export default{
    data() {
      return {
        isShow: false
      }
    },
    methods: {
      showOrhide() {
        var a = 0;
        // 请求数据，赋值 异步渲染
        // 滚动
        // request(()=> {
        //   // 
        //   this.data = ..data
        //   this.$nextTick(()=> {
        //     better
        //   })
        // })
        // 页面渲染完毕，然后执行里面的回调！！！
        // html5 mutationObserver
        // 去渲染页面，是异步的
        this.isShow = !this.isShow
        if(this.isShow) {
          // setTimeout(() => {
          //   this.$refs.input.focus()  
          // }, 200);
          this.$nextTick(()=> {
            this.$refs.input.focus()  
          })
          
        }
      }
    }
  }
</script>