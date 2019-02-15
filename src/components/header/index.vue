<template>
    <div class="header">
        <el-row>
            <top-bar/>
        </el-row>
        <el-row>
            <search-bar/>
        </el-row>
    </div>
</template>
<script>
import TopBar from './topBar';
import SearchBar from './searchBar';

export default {
  components: {
    TopBar,
    SearchBar,
  },
};
</script>

<style lang="less">
    .header {
        box-shadow: 0 2px 27px rgba(0, 0, 0, 0.1)
    }
</style>

