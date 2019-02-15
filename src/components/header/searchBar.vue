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
                    <el-input v-model="searchWord" placeholder="搜索商家或地点" @focus="focus" @blur="blur"></el-input>
                    <el-button type="primary" icon="el-icon-search"></el-button>
                    <dl class="hot-place" v-if="isHotPlace">
                        <dt>热门搜索</dt>
                        <dd v-for="(item, index) in hotPlaceList" :key="index">
                            <router-link :to="{name:'goods', params: {name: item}}">{{item}}</router-link>
                        </dd>
                    </dl>
                    <dl class="search-list" v-if="isSearchList">
                         <dd v-for="(item, index) in searchaList" :key="index">
                            <router-link :to="{name:'goods', params: {name: item}}">{{item}}</router-link>
                        </dd>
                    </dl>
                </div>
                <p class="suggest">
                    <a href="#" v-for="(item, index) in suggestList" :key="index">{{item}}</a>
                </p>
            </el-col>
        </el-row>
    </div>
</template>
<script>
export default {
  data() {
    return {
      searchWord: '',
      // isHotPlace: true,
      // isSearchList: true,
      hotPlaceList: ['京东第一温泉', '度假村7天连锁酒店', '格林豪泰快捷酒店兰庭酒店'], // 热门搜索列表
      searchaList: ['火锅', '火锅底料', '火锅自助'],
      suggestList: ['京东第一温泉', '度假村7天连锁酒店', '格林豪泰快捷酒店兰庭酒店', '99旅馆连锁尚华酒店'],
      isFous: false,
    };
  },
  computed: {
    isHotPlace() {
      return this.isFous && !this.searchWord;
    },
    isSearchList() {
      return this.isFous && this.searchWord;
    },
  },
  methods: {
    focus() {
      this.isFous = true;
    },
    blur() {
      const self = this;
      setTimeout(() => {
        self.isFous = false;
      }, 500);
    },
  },
};
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
            position: relative;
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
            .hot-place{
                position: absolute;
                left: 0;
                top: 68px;
                z-index: 999;
                width: 462px;
                padding:10px 5px;
                box-sizing: border-box;
                font-size: 14px;
                line-height: 2;
                border: 1px solid #ddd;
                border-top: none;
                border-bottom-right-radius: 4px;
                border-bottom-left-radius:4px;
                background-color: #fff;
                box-shadow: 0 3px 5px 0 rgba(0,0,0,0.1);
                dt {
                    padding: 0 5px;
                    font-weight: bold;
                    color:#9c9c9c;
                }
                dd {
                    float: left;
                    padding-left: 5px;
                    a{
                        color: #333;
                    }
                    a:hover {
                        color: #13D1BE;
                    }
                }
            }
            .search-list{
                position: absolute;
                left: 0;
                top: 68px;
                z-index: 999;
                width: 462px;
                box-sizing: border-box;
                font-size: 14px;
                line-height: 2;
                border: 1px solid #ddd;
                border-top: none;
                border-bottom-right-radius: 4px;
                border-bottom-left-radius:4px;
                background-color: #fff;
                box-shadow: 0 3px 5px 0 rgba(0,0,0,0.1);
                a {
                    padding: 0 5px;
                    box-sizing: border-box;
                    display: inline-block;
                    width: 100%;
                    cursor: pointer;
                    color: #999;
                }
                a:hover{
                    background-color: #f8f8f8;
                    color: #13D1BE;
                }
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
