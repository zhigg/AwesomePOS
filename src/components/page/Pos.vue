<template>
  <div class="pos">
    <el-row>
      <el-col :span="7" class="pos-order" id="order_list">
        <el-tabs>
          <el-tab-pane label="点餐">
            <el-table style="width: 100%" border :data="tableData" show-summary>
              <el-table-column prop="goodsName" label="商品名称"></el-table-column>
              <el-table-column prop="count" label="数量" width="50"></el-table-column>
              <el-table-column prop="price" label="金额" width="70"></el-table-column>
              <el-table-column label="操作" width="100" fixed="right">
                <template>
                  <el-button type="text" size="small">删除</el-button>
                  <el-button type="text" size="small">增加</el-button>
                </template>
              </el-table-column>
            </el-table>
            <div style="margin-top:20px;">
              <el-button type="warning">挂单</el-button>
              <el-button type="danger">删除</el-button>
              <el-button type="primary">结账</el-button>
            </div>
          </el-tab-pane>
          <el-tab-pane label="挂单"></el-tab-pane>
          <el-tab-pane label="外卖"></el-tab-pane>
        </el-tabs>
      </el-col>
      <el-col :span="17">
        <div class="often-goods">
          <div class="title">常用商品</div>
          <div class="often-goods-list">
            <ul>
              <li v-for="item in oftenGoods" :key="item.goodsId">
                <span>{{item.goodsName}}</span>
                <span class="o-price">￥{{item.price}}元</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="goods-type">
          <el-row>
            <el-col>
              <el-tabs>
                <el-tab-pane label="汉堡">
                  <ul class="cookList">
                    <li>
                      <span class="foodImg">
                        <img src="http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg" width="100%" />
                      </span>
                      <span class="foodName">香辣鸡腿堡</span>
                      <span class="foodPrice">￥20.00元</span>
                    </li>
                  </ul>
                </el-tab-pane>
                <el-tab-pane label="小食">小食</el-tab-pane>
                <el-tab-pane label="饮料">饮料</el-tab-pane>
                <el-tab-pane label="套餐">套餐</el-tab-pane>
              </el-tabs>
            </el-col>
          </el-row>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "pos",
  data() {
    return {
      tableData: [
        {
          goodsName: "可口可乐",
          price: 8,
          count: 1
        },
        {
          goodsName: "香辣鸡腿堡",
          price: 15,
          count: 1
        },
        {
          goodsName: "爱心薯条",
          price: 8,
          count: 1
        },
        {
          goodsName: "甜筒",
          price: 8,
          count: 1
        }
      ],
      oftenGoods: [
        {
          goodsId: 1,
          goodsName: "香辣鸡腿堡",
          price: 18
        },
        {
          goodsId: 2,
          goodsName: "田园鸡腿堡",
          price: 15
        },
        {
          goodsId: 3,
          goodsName: "和风汉堡",
          price: 15
        },
        {
          goodsId: 4,
          goodsName: "快乐全家桶",
          price: 80
        },
        {
          goodsId: 5,
          goodsName: "脆皮炸鸡腿",
          price: 10
        },
        {
          goodsId: 6,
          goodsName: "魔法鸡块",
          price: 20
        },
        {
          goodsId: 7,
          goodsName: "可乐大杯",
          price: 10
        },
        {
          goodsId: 8,
          goodsName: "雪顶咖啡",
          price: 18
        },
        {
          goodsId: 9,
          goodsName: "大块鸡米花",
          price: 15
        },
        {
          goodsId: 20,
          goodsName: "香脆鸡柳",
          price: 17
        }
      ]
    };
  },
  mounted() {
    var orderHeight = document.body.clientHeight;
    document.getElementById("order_list").style.height = orderHeight + "px";
  }
};
</script>

<style scoped>
.pos-order {
  background-color: #f9fafc;
  border-right: 1px solid #c0ccda;
}
.pos {
  height: 100%;
}
.title {
  height: 20px;
  border-bottom: 1px solid #d3dce6;
  background-color: #f9fafc;
  padding: 10px;
}
.often-goods-list ul li {
  list-style: none;
  float: left;
  border: 1px solid #e5e9f2;
  padding: 10px;
  margin: 5px;
  background-color: #fff;
}
.o-price {
  color: #58b7ff;
}
.cookList li{
       list-style: none;
       width:23%;
       border:1px solid #E5E9F2;
       height: auot;
       overflow: hidden;
       background-color:#fff;
       padding: 2px;
       float:left;
       margin: 2px;
 
   }
   .cookList li span{
       
        display: block;
        float:left;
   }
   .foodImg{
       width: 40%;
   }
   .foodName{
       font-size: 18px;
       padding-left: 10px;
       color:brown;
 
   }
   .foodPrice{
       font-size: 16px;
       padding-left: 10px;
       padding-top:10px;
   }
</style>
