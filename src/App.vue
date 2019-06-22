<template>
  <div id="app">
    <div id="nav">
      <el-row>
        <el-button>默认按钮</el-button>
        <el-button type="primary">主要按钮</el-button>
        <el-button type="success">成功按钮</el-button>
        <el-button type="info">信息按钮</el-button>
        <el-button type="warning">警告按钮</el-button>
        <el-button type="danger">危险按钮</el-button>
      </el-row>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  data () {
    return {
      formData:{
        name:'',
        bio:''
      }
    }
  },
  crreated(){
    this.handleSubmit () 
  },
  methods: {
    handleSubmit () {
      const id=this.$route.params.id
      axios({
        method: 'GET',
        url:`http//:localhost:3000/${id}`
      }).then(res=>{
        this.formData=res.data
      })
    }
  }
}
</script>


<style lang="less">
</style>
