<template>
<div class="page-index">
    <el-row class="column-one">
        <el-col :span="5">
            <my-menu />
        </el-col>
         <el-col :span="19">
            life
        </el-col>
    </el-row>
    <el-row>
         <el-col :span="24">
            container
        </el-col>
    </el-row>
</div>
</template>

<script>
import MyMenu from '@/components/index/menu'
export default {
    components: {
        MyMenu,
    }
}
</script>

<style lang="less" scoped>
    .page-index {
        width: 1190px;
        margin: 0 auto;
    }
    .column-one {
        // width: 1190px;
        // margin: -50px auto 0 ;
        // z-index: 9999;
    }
</style>

