<template>
    <div class="m-menu">
        <dl class="nav" @mouseleave="menuLeave()">
            <dt>全部分类</dt>
            <!-- <dd>美食
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>
                外卖
                <i class="el-icon-arrow-right"></i>
            </dd> -->
            <dd v-for="(item, index) in detailList" :key="index" @mouseenter="showContent(item)" >
                {{item.title}}
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>酒店
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>榛果民宿
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>猫眼电影
                <i class="el-icon-arrow-right"></i>
            </dd>
              <dd>机票 / 火车票
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>休闲娱乐 / KTV
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>生活服务
                <i class="el-icon-arrow-right"></i>
            </dd>
               <dd> 丽人 / 美发 / 医学美容
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>结婚 / 婚纱摄影 / 婚宴
                <i class="el-icon-arrow-right"></i>
            </dd>
              <dd>亲子 / 儿童乐园 / 幼教
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>运动健身 / 健身中心
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>家装 / 建材 / 家居
                <i class="el-icon-arrow-right"></i>
            </dd>
           <dd>学习培训 / 音乐培训
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>医疗健康 / 宠物 / 爱车
                <i class="el-icon-arrow-right"></i>
            </dd>
            <dd>酒吧 / 密室逃脱
                <i class="el-icon-arrow-right"></i>
            </dd>
            <div class="detail" v-show="contentList">
                <template v-for="(item2, index2) in contentList" >
                   <h2 :key="index2">
                       {{item2.title}}
                       <span class="link-more">
                           <a href="#">更多</a>
                            <i class="el-icon-arrow-right"></i>
                       </span>
                   </h2>
                   <span v-for="(v, i) in item2.content" :key="v + '_' + i">{{v}}</span>
                </template>
                 <!-- <template>
                   <h2>美食
                       <span class="link-more">
                           <a href="#">更多</a>
                            <i class="el-icon-arrow-right"></i>
                       </span>
                   </h2>
                   <span>代金券</span>
                   <span>甜点</span>
                   <span>火锅</span>
                   <span>自助餐</span>
                   <span>小吃</span>
                   <span>快餐</span>
                   <span>日韩料理</span>
                   <span>西餐</span>
                   <span>聚餐宴请</span>
                   <span>烧烤</span>
                   <span>烤肉</span>
                   <span>东北菜</span>
                   <span>川湘菜</span>
                   <span>香锅烤鱼</span>
                </template> -->
            </div>

        </dl>
        
    </div>
</template>

<script>
export default {
    data() {
        return {
            detailList:
                [{
                    title: '美食 / 吃货',
                    icon: '',
                    children: [{
                        title: '美食',
                        content:['代金券', '甜点', '火锅', '自助餐']
                    },{
                        title: '吃货',
                        content: ['吃天下', '烤肉', '烧烤', '西餐']
                    }]
                },{
                    title: '外卖',
                    icon: '',
                    children:[{
                        title: '外卖',
                        content:['美团', '饿了么', '哈哈']
                    }]
                }],
            contentList:[],
        }
    },
    methods: {
        showContent(item) {
            this.contentList = item.children
        },
        menuLeave() {
            this.contentList = null
        }
    }
}

</script>

<style lang="less" scoped>
    .m-menu {
        position: relative;
        background: linear-gradient(-90deg,rgba(2,181,157,.85) 2%,rgba(22,146,183,.85) 100%);
        dl {
            position: relative;
        }
        .nav {
        }
        dt,dd {
            color: #fff;
        }
        dt {
            line-height: 4;
            padding: 0 10px;
        }
        dd {
            padding: 0 10px;
            line-height: 2;
            font-size: 14px;
            cursor: pointer;
        }
        dd:hover {
            background-color: rgba(255,255,255,.2);
        }
        dd i {
            float: right;
            line-height: 2;
        }
        .detail {
            // display: none;
            position: absolute;
            left: 248px;
            top: 64px;
            width: 400px;
            height: 448px;
            padding: 0 40px;
            z-index: 9999;
            color: #999;
            background-color: #fff;
            h2 {
                margin-top: 20px;
                font-size: 16px;
                font-weight: normal;
                line-height: 3;
                border-bottom: 1px solid #ddd;
                color: #222;
                .link-more {
                    float: right;
                    line-height: 49px;
                     cursor: pointer;
                    font-size: 12px;
                }
                a {
                    color: #999;
                }
                .link-more:hover {
                    color: #31BBAC;
                    a {
                        color: #31BBAC;
                    }
                }
            }
            >span {
                margin-top: 8px;
                margin-right: 6px;
                font-size: 12px;
                cursor: pointer;
            }
            span:hover {
                color: #31BBAC;
            }
        }
        .nav:hover {
          .detail {
                display: block!important;
            }  
        }
        
        

    }
</style>






