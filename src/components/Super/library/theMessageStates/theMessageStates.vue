<!--
*@描述:信息显示组件
*@版本:V1.0
*@作者:白爱民
*@Date:2020年3月28日08:22:14
*@最后修改人:白爱民
*@LastEditTime:2020年3月28日08:22:14
*@说明：-->
<template>
  <div>
    <!-- 下拉框所有内容 -->
    <van-collapse class="publicClassification" v-model="activeNames" accordion>
      <!-- 折叠面板 -->
      <van-collapse-item :title="title" name="1">
        <!-- 左滑显示添加删除等 -->
        <van-swipe-cell>
          <!-- 不同下拉框里面不同内容 -->
          <div class="bodyDiv">
            <infoShow></infoShow>
          </div>

          <!-- 左滑显示的内容 -->
          <template #right>
            <van-button
              @click="useComponent()"
              square
              text="使用"
              type="primary"
              class="delete-button"
            />
            <van-button
              @click="disableComponent()"
              square
              text="停用"
              type="danger"
              class="delete-button"
            />
          </template>
        </van-swipe-cell>
      </van-collapse-item>
    </van-collapse>
  </div>
</template>
<style scoped>
.goods-card {
  margin: 0;
  background-color: @white;
}

.delete-button {
  height: 100%;
}
</style>
<script>
import infoShow from "./infoShow";
import swipeCell from "../../template/swipeCell"; // 左右滑动

export default {
  components: {
    infoShow,
    swipeCell
  },
  props: {
    titleP: { default: "信息显示组件" }
  },
  data() {
    return {
      activeNames: "1",
      // list: [{ title: "信息显示组件" }]
      title: ""
    };
  },

  watch: {
    titleP(newVal) {
      this.title = newVal;
    }
  },
  mounted() {
    this.title = this.titleP;
  },
  methods: {
    // 组件右划使用按钮操作
    useComponent() {
      console.log(0);
    },

    // 组件右划停用按钮操作
    disableComponent() {}
  }
};
</script>
