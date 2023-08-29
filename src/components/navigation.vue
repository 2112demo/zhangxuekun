<template lang="">
  <div class='box'>
    <div class='box-top'>
      <div>
        <span class="iconfont icon-cloud"></span>
        <h1 class='box-top-title'>{{msg}}</h1>
      </div>
    </div>
    <div class='nav'>
      <ul>
        <li v-for='item in list' :key='item.id'>
          <p>{{item.title}}</p>
          <ul>
            <li v-for='cont in item.cont' :key='cont.id'>
              <span class="iconfont" :class="cont.icon"></span>
              <h3 @click="changeIndex(cont.id)">
                <router-link :to="cont.router" class='lin'>
                  {{cont.name}}
                </router-link>
              </h3>
              <dl :class="{'height0': showIndex === cont.id ? false : true}">
                <dd v-for='list in cont.list' :key='list.id' @click='_active(list.id)'>
                  <span>></span>
                  <router-link :to="list.router" class='link' :class="{active: list.id===active}">{{list.name}}</router-link>
                </dd>
              </dl>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: 'navigator',
  props: {
    msg: String
  },
  data () {
    return {
      // list.cont.list的id
      showIndex: '',
      active: 0,
      list: [
        {
          id: 1,
          title: '常用操作',
          cont: [
            {id: 1, name: '首页', icon: 'icon-shouye', 'router': '/'}
          ]
        },
        {
          id: 2,
          title: '业务管理',
          cont: [
            {
              id: 2,
              name: '项目任务',
              icon: 'icon-daichuli',
              'router': '',
              list: [
                {id: 1, name: '批量新建订单', 'router': '/project1'},
                {id: 2, name: '项目列表', 'router': '/project2'},
                {id: 3, name: '任务派单', 'router': '/project3'},
                {id: 4, name: '订单列表', 'router': '/project4'}
              ]
            },
            {
              id: 3,
              name: '资金发票',
              icon: 'icon-fs_expense',
              'router': '',
              list: [
                {id: 5, name: '资金发票', 'router': '/project5'}
              ]
            },
            {
              id: 4,
              name: '企业管理',
              icon: 'icon-qiyeguanli',
              'router': '',
              list: [
                {id: 6, name: '安全', 'router': '/project6'}
              ]
            }
          ]
        },
        {
          id: 3,
          title: '服务中心',
          cont: [
            {
              id: 5,
              name: '身份&安全',
              icon: 'icon-zhanghaoyuanquan',
              'router': ''
            }
          ]
        }
      ]
    }
  },
  methods: {
    // 点击下标事件
    changeIndex (id) {
      // 如果点击的是同一个元素，则让showIndex 回到 null  都关闭了
      if (this.showIndex === id) {
        // eslint-disable-next-line no-return-assign
        return this.showIndex = null
      }
      this.showIndex = id
      // console.log(this.showIndex)
    },
    _active (id) {
      this.active = id
    }
  }
}
</script>
<style lang="">
  .box-top{
    background-color: red;
    color: #fff;
  }
  .box-top div{
    display: flex;
    height: 64px;
    justify-content: center;
    align-items: center;
  }
  .icon-cloud{
    font-size: 30px;
  }
  .box-top-title{
    margin-left: 6px;
    font-size: 18px;
  }
  .height0{
    height: 0;
    overflow: hidden;
  }
  /* 导航栏内容 */
  .nav{
    padding: 14px 20px 40px;
  }
  .nav>ul>li>p{
    text-align: start;
    color: #868e96;
    font-size: 14px;
  }
  .nav>ul>li>ul>li{
    display: flex;
    flex-wrap: wrap;
    justify-content: start;
    align-items: center;
    margin: 32px 0 32px 12px;
    width: 150px;
  }
  .nav>ul>li>ul>li>span{
    font-size: 27px;
    margin-right: 14px;
  }
  .nav>ul>li>ul>li>h3{
    font-size: 18px;
    color: #616870;
  }
  .nav>ul>li>ul>li>dl{
    color: #90939f;
    margin-left: 15px;
    text-align: start;
  }
  .nav>ul>li>ul>li>dl>dd{
    margin: 10px 0;
  }
  .nav>ul>li>ul>li>dl>dd>.link{
    padding-left: 10px;
    color: #616f7d;
    text-decoration: none;
  }
  .lin{
    color: #616f7d;
    text-decoration: none;
  }
  .active{
    color: #2c4198 !important;
    font-weight: 700;
  }
</style>
