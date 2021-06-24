<template>
  <div class="ic-body">
    <div class="header-bar">
      <img class="left-arrow" :src="backImg" />
      <span>账户明细</span>
      <img class="more" :src="moreImg" />
    </div>
    <div>
      <img class="header-img" :src="headerImg" />

      <div class="el-tabs">
        <p>当天</p>
        <p>七天</p>
        <p>一个月</p>
        <p class="active-span">更多筛选</p>
      </div>

      <div class="time-style">
        <p>2020/12/07-2021/06/07</p>
      </div>

      <div class="inprice">
        <div style="color: green">
          <p style="font-size: 18px;">支出</p>
          <p style="font-size: 18px;">272116.02</p>
        </div>

        <div class="left-price"></div>

        <div style="color: red">
          <p style="font-size: 18px;">收入</p>
          <p style="font-size: 18px;">272093.49</p>
        </div>
      </div>
    </div>

    <div class="bottom-content" v-for="item in dataList" :key='item.titleTime'>
      <p style="font-weight: 700">{{item.titleTime}}</p>
      <ul>
        <li v-for="(subItem, index) in item.details" :key='index'>
          <div class="detail-text">
            <p>
              <span style="font-size: 16px">{{subItem.moneyTitle}}</span>
              <span style="float: right">{{subItem.moneyCounts}}</span>
            </p>
            <p class="sub-content">
              <span>{{subItem.subTitle}}</span>
              <span style="float: right">{{subItem.subMoney}}</span>
            </p>
          </div>
          <img :src="rightImg" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { Tabs } from "ant-design-vue";

export default {
  components: {
    "e-tabs": Tabs,
    "e-tab-pane": Tabs.TabPane,
  },
  data() {
    return {
      backImg: require("../assets/back.png"),
      moreImg: require("../assets/more.png"),
      headerImg: require("../assets/header.png"),
      tabsImg: require("../assets/tabs.jpg"),
      rightImg: require("../assets/right.png"),
      activeName: "more",
      dataList: [
        {
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        }, {
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        }, {
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        },
        {
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        }, {
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        }, {
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        }, {
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        },{
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        },{
          titleTime: '5月26日 周三',
          details: [
            { moneyTitle: '工资', moneyCounts: '+7458.61', subTitle: '工资', subMoney: '余额: 7526.80' },
          ]
        }

      ]
    };
  },
  methods: {
    onTabChanged(e) {
      console.log(e);
    },
  },
};
</script>

<style lang="scss" scope>
* {
  margin: 0;
  padding: 0;
}

.header-bar {
  width: 100%;
  height: 48px;
  background-color: #006cbd;
  padding: 9px 16px;

  .left-arrow {
    width: 30px;
    height: 30px;
    float: left;
  }

  span {
    align-items: center;
    color: #ffffff;
    font-size: 20px;
    text-align: center;
  }

  .more {
    width: 30px;
    height: 30px;
    float: right;
  }
}

.header-img {
  height: 148px;
  width: 100vw;
}

.el-tabs {
  display: flex;
  justify-content: space-around;
  padding: 12px 16px 0 16px;
  border-bottom: 1px solid #f5f5f5;

  p {
    font-weight: 400;
    text-align: center;
    padding-bottom: 10px;
  }

  .active-span {
    color: #006cbd;
    font-weight: 700;
    border-bottom: 4px solid #0080c2;
  }
}

.time-style {
  margin-top: 20px;
  p {
    display: inline-flex;
    background-color: #f5f5f5;
    border-radius: 50px;
    padding: 4px 12px;
  }
}

.inprice {
  display: flex;
  justify-content: space-around;
  padding: 22px 16px;
}

.left-price {
  height: 48px;
  border-right: 1px solid #f5f5f5;
  border-right-width: 1px;
}

.bottom-content {
  width: 100%;
  border-top: 10px solid #f5f5f5;
  margin-top: 10px;
  padding: 12px 20px 10px 20px;

  p {
    text-align: left;
  }

  ul {
    padding-right: 20px;
  }

  li {
    width: 100%;
    display: flex;
    align-items: center;
    border-bottom: 1px solid #f5f5f5;
    padding: 18px 0;

    p {
      font-size: 15px;
    }

    .detail-text {
      width: 100%;
      flex: 1;

      .sub-content {
        color: #a4a4a4;
        font-size: 14px;
        margin-top: 6px;
      }
    }

    img {
      height: 16px;
      margin-left: 8px;
    }
  }
}

li:last-child {
  border-bottom: 0px;
}
</style>
