<template>
    <div class="layout-default">
        <el-container>
            <el-header height="">
                <my-header />
            </el-header>
            <el-main>
                <router-view></router-view>
            </el-main>
            <el-footer height="">
                <my-footer />
            </el-footer>
        </el-container>
    </div>
</template>

<script>
import MyHeader from '@/components/header/index';
import MyFooter from '@/components/footer/index';

export default {
  components: {
    MyHeader,
    MyFooter,
  },
};
</script>

<style lang="less">
   @import "../assets/css/public/layout.less";
   .el-header, .el-main {
       padding: 0;
   }
   .el-main {
       margin-top: -50px;
   }
</style>
