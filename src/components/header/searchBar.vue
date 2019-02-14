<template>
    <div class="search-bar">
        <el-row class="m-header-searchbar">
            <el-col :span="6" class="left">
                <a href="/">
                    <img src="https://s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png" alt="">
                </a>
            </el-col>
            <el-col :span='15' class="center"> 
                <div class="wrapper">
                    <el-input v-model="searchWord" placeholder="搜索商家或地点"></el-input>
                    <el-button type="primary" icon="el-icon-search"></el-button>
                    <dl class="hot-place" v-if="isHotPlace">
                        <dt>热门搜索</dt>
                        <dd>
                            <router-link to="/">京东第一温泉</router-link>
                        </dd>
                        <dd>
                            <router-link to="/">度假村7天连锁酒店</router-link>
                        </dd>
                        <dd>
                           <router-link to="/">格林豪泰快捷酒店兰庭酒店</router-link> 
                        </dd>
                        <dd>
                            <router-link to="/">99旅馆连锁尚华酒店</router-link>
                        </dd>
                    </dl>
                    <dl class="search-list" v-if="isSearchList">
                        <dd>
                            <router-link to="/">火锅</router-link>
                        </dd>
                        <dd>
                            <router-link to="/">火锅底料</router-link>
                        </dd>
                        <dd>
                            <router-link to="/">火锅自助</router-link>
                        </dd>
                    </dl>
                </div>
                <p class="suggest"> 
                    <router-link to="/">京东第一温泉</router-link>
                    <router-link to="/">度假村7天连锁酒店</router-link>
                    <router-link to="/">格林豪泰快捷酒店兰庭酒店</router-link>
                    <router-link to="/">99旅馆连锁尚华酒店</router-link>
                </p>
            </el-col>
        </el-row>
    </div>
</template>
<script>
export default {
    data(){
        return {
            searchWord: '',
            isHoisHotPlace: false,
            isSearchList: false,
        }
    }
}
</script>

<style lang="less">
    .search-bar {
        width: 100%;
        padding-bottom: 35px;
        background-color: #fff;
        .m-header-searchbar{
            width: 1190px;
            margin: 0 auto;
            .el-col {
                display: inline-block;
            }
        }
        .left {
            position: relative;
            padding: 28px 60px 40px 0;
            h1 {
                position: absolute;
                left:0;
                top:0;
                z-index: 11;
            }
            img {
                width: 126px;
                height: 46px;
            }
        }
        .center .wrapper {
            
            display: flex;
            padding-top: 28px;
            .el-input {
                width: 462px;
            }
            input {
                padding: 10px;
                border-top-right-radius: 0;
                border-bottom-right-radius: 0;
                border: 1px solid #13D1BE;
                border-right: none;
            }
            input::placeholder{
                font-size: 14px;
                color: #999;
            }
            .el-icon-search {
                font-size: 20px;
            }
            button {
                width: 88px;
                padding: 0;
                 border-top-left-radius: 0;
                border-bottom-left-radius: 0;
                background-color: #13D1BE;
                border: 1px solid transparent;
            }
        }
        .suggest {
                font-size: 12px;
                color: #999;
                a { 
                    display: inline-block;
                    padding-top: 8px;
                    padding-left: 12px;
                    color: #999;
                }
                a:hover {
                    color: #13D1BE;
                }
        }
    }
</style>
