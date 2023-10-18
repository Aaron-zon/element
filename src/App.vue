<!-- 34 -->
<template>
  <div id="app">
    <el-row>
      <el-col :span="24">
        <div class="grid-content bg-purple-dark"></div>
      </el-col>
    </el-row>

    <h1>分栏间隔</h1>
    <el-row :gutter="20">
      <el-col :span="12">
        <div class="grid-content bg-purple-dark"></div>
      </el-col>
      <el-col :span="12">
        <div class="grid-content bg-purple-dark"></div>
      </el-col>
    </el-row>

    <el-row :gutter="20">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>
    
    <h1>混合布局</h1>
    <el-row :gutter="20">
      <el-col :span="16"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="8"><div class="grid-content bg-purple"></div></el-col>
    </el-row>

    <h1>分栏偏移 offset</h1>
    <el-row :gutter="20">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6" :offset="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>
    <el-row :gutter="20">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6" :offset="12"><div class="grid-content bg-purple"></div></el-col>
    </el-row>

    <h1>分栏偏移 push</h1>
    <el-row :gutter="20">
      <el-col :span="6" :push="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>

    <h1>分栏偏移 pull</h1>
    <el-row :gutter="20">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6" :pull="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>

    <h1>对齐方式</h1>
    <el-row type="flex" class="row-bg">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>
    <el-row type="flex" class="row-bg" justify="center">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>
    <el-row type="flex" class="row-bg" justify="end">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>
    <el-row type="flex" class="row-bg" justify="space-between">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>
    <el-row type="flex" class="row-bg" justify="space-around">
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
    </el-row>

    <h1>响应式布局</h1>
    <el-row :gutter="10">
      <el-col :xs="8" :sm="6" :md="4" :lg="3" :xl="1"><div class="grid-content bg-purple"></div></el-col>
      <el-col :xs="4" :sm="6" :md="8" :lg="9" :xl="11"><div class="grid-content bg-purple-light"></div></el-col>
      <el-col :xs="4" :sm="6" :md="8" :lg="9" :xl="11"><div class="grid-content bg-purple"></div></el-col>
      <el-col :xs="8" :sm="6" :md="4" :lg="3" :xl="1"><div class="grid-content bg-purple-light"></div></el-col>
    </el-row>

    <h1>基于断点的隐藏类</h1>
    <div class="hidden-xs-only grid-content bg-purple">当视口在 xs 768 尺寸时隐藏</div>
    <div class="hidden-sm-only grid-content bg-purple">当视口在 sm 768-992 尺寸时隐藏</div>
    <div class="hidden-sm-and-down grid-content bg-purple">当视口在 sm 992及以下尺寸时隐藏</div>
    <div class="hidden-sm-and-up grid-content bg-purple">当视口在 sm 992及以上尺寸时隐藏</div>
    <div class="hidden-md-only grid-content bg-purple">当视口在 md 992-1200尺寸时隐藏</div>
    <div class="hidden-md-and-down grid-content bg-purple">当视口在 md 1200及以下尺寸时隐藏</div>
    <div class="hidden-md-and-up grid-content bg-purple">当视口在 md 1200及以上尺寸时隐藏</div>
    <div class="hidden-lg-only grid-content bg-purple">当视口在 lg 1200-1920尺寸时隐藏</div>
    <div class="hidden-lg-and-down grid-content bg-purple">当视口在 lg 1920及以下尺寸时隐藏</div>
    <div class="hidden-lg-and-up grid-content bg-purple">视口在 lg 1920及以上尺寸时隐藏</div>
    <div class="hidden-xl-only grid-content bg-purple">当视口在 xl 尺寸时隐藏</div>


  </div>
</template>

<script>
import ElRow from "@/components/element/Row.vue";
import ElCol from "@/components/element/Col.vue";
export default {
  name: "app",
  components: {
    ElRow,
    ElCol,
  }
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
}
#app .el-row {
  margin-bottom: 10px;
}
.el-row {
  margin-bottom: 20px;
  &:last-child {
    margin-bottom: 0;
  }
}
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #d3dce6;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
  margin-bottom: 20px;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}
</style>