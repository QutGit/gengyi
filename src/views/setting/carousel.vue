<template>
  <el-container>
    <el-header><h1>首页轮播</h1></el-header>
    <!-- 筛选区域 -->
    <el-main>
      <el-form class="fp-form" label-position="right" :inline="true" ref="form" :model="form" label-width="70px">
        <div class="fp-form-footer">
          <div class="pull-right">
            <el-button type="primary" @click="add()">添加</el-button>
          </div>
        </div>
      </el-form>
    </el-main>
    <!-- 列表区域 -->
    <el-main>
      <el-table key="btable" :data="reconcList" v-loading="loading">
        <el-table-column prop="settlement_cycle" label="轮播图名称"></el-table-column>
        <el-table-column prop="agency_settlement_prices" label="轮播图名称"></el-table-column>
        <el-table-column prop="middleground_settlement_prices" label="轮播图地址"></el-table-column>
      </el-table>
    </el-main>
    <el-dialog title="添加轮播" :visible.sync="showDialog" width="40%">
      <el-form :model="form">
        <el-form-item label="活动名称" :label-width="formLabelWidth">
          <el-input v-model="form.name" placeholder="请输入逗号隔开的文章ID" autocomplete="off"></el-input>
        </el-form-item>
      </el-form>
      <span slot="footer" class="dialog-footer">
        <el-button @click="showDialog = false">取 消</el-button>
        <el-button type="primary" @click="save()">保存</el-button>
      </span>
    </el-dialog>
  </el-container>
</template>

<script>

export default {
  name: 'Login',
  data() {
    return {
      loading: false,
      showDialog: false,
      formLabelWidth: '100px',
      form: {
        name: ''
      }
    }
  },
  mounted() {

  },
  methods: {
    add() {
      this.showDialog = true
    },
    save() {
      this.showDialog = false
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
