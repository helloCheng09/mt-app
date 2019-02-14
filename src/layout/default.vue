<template>
    <div class="layout-default">
        <el-container>
            <el-header height="">
                <my-header />
            </el-header>
            <el-main>Main</el-main>
            <el-footer height="">Footer</el-footer>
        </el-container>
    </div>
</template>

<script>
import MyHeader from '@/components/header/index'
export default {
    components: {
        MyHeader
    }
}
</script>

<style lang="less">
   @import "../assets/css/public/layout.less";
   .el-header {
       padding: 0;
   }
</style>
