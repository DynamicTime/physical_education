<!--
*@描述:test
*@版本:V1.0
*@作者:白爱民
*@Date:2019年12月11日20:16:26
*@最后修改人:herry
*@LastEditTime:2019年12月11日20:16:31
*@说明：-->
<template>
  <div>
    <van-action-sheet v-model="siteUserShow" title="图片信息">
      <!-- <div class="content"></div> -->
      <div class="body">
        <van-field v-model="text" label="组件名称" placeholder="请输入名称" />

        <div class="isTrue" v-for="(item,i) in isTrueList">
          <van-cell center :title="isTrueList[i].name">
            <template #right-icon>
              <van-switch v-model="isTrueList[i].isTrue" size="24" />
            </template>
          </van-cell>
        </div>
      </div>
    </van-action-sheet>
  </div>
</template>
<style scoped>
.body {
  height: 350px;
}
.isTrue {
  margin-top: 2px;
}

/* van组件所有居左 */
>>> .van-cell__title,
.van-cell__value {
  text-align: left;
}

/* van组件所有字体大小 */
>>> .van-cel {
  font-size: 20px;
}
</style>

<script>
export default {
  props: {
    siteUserShowP: "",
    isTrueListP: { type: Array, default: () => {} }
  },
  data() {
    return {
      siteUserShow: false, //  初始化底部弹框默认为false
      text: "",
      checked: "",
      isTrueList: [
        { name: "姓名是否显示", isTrue: true },
        { name: "性别是否显示", isTrue: true },
        { name: "学号是否显示", isTrue: true },
        { name: "学院是否显示", isTrue: true },
        { name: "专业是否显示", isTrue: true },
        { name: "班级是否显示", isTrue: true },
        { name: "年级是否显示", isTrue: true }
      ],
      isTrue: []
    };
  },
  watch: {
    // 监听父页面传来数据
    siteUserShowP(newVal) {
      if (newVal == true) {
        this.siteUserShow = newVal;
      }
      //  this.nameIsTrue=[]
      // for (let i = 0; i < newVal.length; i++) {
      //   this.nameIsTrue[i] = newVal[i];
      // }
    },

    isTrueListP(newVal) {
      console.log("我是isTrueListP===>" + newVal)
      for (let i = 0; i < newVal.length; i++) {
        this.isTrueList[i].isTrue =  newVal[i]
        
      }
    },

    // 退出后返回给父页面数据
    siteUserShow(newVal) {
      this.$emit("listenUserToMakeForm", newVal, this.isTrueList);

      //   console.log(this.isTrueList)
    }
  },
  mounted() {},
  methods: {}
};
</script>
