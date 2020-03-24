<!--
*@描述:用户信息组件
*@版本:V1.0
*@作者:白爱民
*@Date:2019年12月11日20:16:26
*@最后修改人:herry
*@LastEditTime:2019年12月11日20:16:31
*@说明：-->
<template>
  <div>
    <div class="body">
      <div class="picture">
        <img :src="picInfo" alt />
      </div>

      <!-- <div class="rightData">
        <div class="info" v-for="(item ,i) in infoName" v-if="nameIsTrue[i]">
          <div class="infoName">{{infoName[i].name}}</div>
          <div class="infoData">{{infoName[i].data}}</div>
        </div>
      </div>-->

      <div class="rightDiv">
        <table
          class="rightTable"
          width="200"
          border="1"
          cellspacing="0"
          cellpadding="0"
          align="center"
        >
          <tr v-for="(item ,i) in infoName" v-if="nameIsTrue[i]">
            <td width="300">{{infoName[i].name}}</td>
            <td>{{infoName[i].data}}</td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>
<style scoped>
.rightDiv {
  height: 190px;
  border: 1px solid white;

  /* 使上下居中 */
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
.rightTable {
  text-align: center;
  border: 1px solid white;
  color: black;
  font-size: 15px;
}
.body {
  width: 298px;
  max-width: auto;
  height: 190px;
  border: 1px solid;
  /* position: relative; */
}
.picture img {
  width: 100px;
  height: 120px;
  margin: 30px auto;
}
.body .picture {
  float: left;
  width: 100px;
  height: 140px;
  top: 4px;
  bottom: 4px;
  border: 1px solid white;
  /* position: absolute; */
}

/* 左边大边框 */
.body .rightData {
  width: 176px;
  height: 190px;
  position: absolute;
  left: 120px;
  border: 1px solid white;
  font-size: 15px;
  text-align: left;
  color: black;
}

/* 每行数据边框 */
.body .info {
  border: 1px solid white;
  /* display:inline-block; */
}

/* 每行数据左边的属性边框 */
.infoName {
  margin-right: 20px;
  display: inline-block;
  border: 1px solid white;
}
/* 每行数据左边的数据边框 */
.infoData {
  display: inline-block;
  border: 1px solid white;
}
</style>
<script>
export default {
  props: {
    isTrueList: {
      type: Array,
      default: () => [true, true, true, true, true, true, true]
    }
    // isTrueList:Array
  },
  data() {
    return {
      infoName: [
        { name: "名字", data: "张三" },
        { name: "性别", data: "男" },
        { name: "学号", data: "122231231231" },
        { name: "学院", data: "建工学院" },
        { name: "专业", data: "电子信息" },
        { name: "班级", data: "二班" },
        { name: "年级", data: "一年级" }
      ],
      picInfo: require("../../../assets/super/user.png"),

      nameIsTrue: [true, true, true, true, true, true, true]
    };
  },
  watch: {
    isTrueList(newVal) {
      this.nameIsTrue=[]
      for (let i = 0; i < newVal.length; i++) {
        this.nameIsTrue[i] = newVal[i];
      }
      console.log("我是监听isTRUEList中的newVal==>>" + newVal);

      console.log("我是监听isTRUEList中的nameISTrue===>" + this.nameIsTrue);
      // console.log("我是isTrueList监听中isTrueList===>"+newVal);

      // console.log("我是isTrueList监听中isTrueList===>"+this.isTrueList);

      // console.log("我是isTrueList监听中infoName===>"+this.infoName.isTrue);
    }
  },
  mounted() {
    // this.start();
  },
  methods: {
    start() {
      for (let i = 0; i < this.isTrueList.length; i++) {
        this.nameIsTrue[i] = this.isTrueList[i];
      }

      console.log("我是start中的infoName" + this.isTrueList);
    }
  }
};
</script>
