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
              <h3 @click="changeIndex(cont.id)">{{cont.name}}</h3>
              <dl :class="{'height0': showIndex === cont.id ? false : true}">
                <dd v-for='list in cont.list' :key='list.id'>
                  <span>></span>
                  <router-link to="">{{list.name}}</router-link>
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
      list: [
        {
          id: 1,
          title: '常用操作',
          cont: [
            {id: 1, name: '首页', icon: 'icon-shouye'}
          ]
        },
        {
          id: 2,
          title: '业务管理',
          cont: [
            {
              id: 201,
              name: '项目任务',
              icon: 'icon-daichuli',
              list: [
                {id: 1, name: '批量新建订单', 'router': '/project1'},
                {id: 2, name: '项目列表', 'router': '/project2'},
                {id: 3, name: '任务派单', 'router': '/project3'},
                {id: 4, name: '订单列表', 'router': '/project4'}
              ]
            },
            {
              id: 202,
              name: '资金发票',
              icon: 'icon-fs_expense',
              list: [
                {id: 1, name: '资金发票', 'router': '/project5'}
              ]
            },
            {
              id: 203,
              name: '企业管理',
              icon: 'icon-qiyeguanli',
              list: [
                {id: 1, name: '安全', 'router': '/project6'}
              ]
            }
          ]
        },
        {
          id: 3,
          title: '服务中心',
          cont: [
            {
              id: 1,
              name: '身份&安全',
              icon: 'icon-zhanghaoyuanquan'
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
      console.log(this.showIndex)
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
</style>
