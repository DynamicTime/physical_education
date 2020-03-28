<!--
*@描述:用户信息组件
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
        <div class="componentBody" v-for="(item,index) in componentList">
          <!-- 左滑显示添加删除等 -->
          <van-swipe-cell>
            <!-- 不同下拉框里面不同内容 -->
            <user v-if="componentList[index].isTrue && componentList[index].position ==0"></user>
            <!-- 左滑显示的内容 -->
            <template #right>
              <van-button
                @click="disableComponent()"
                square
                text="停用"
                type="danger"
                class="delete-button"
              />
            </template>
          </van-swipe-cell>
        </div>
      </van-collapse-item>
    </van-collapse>
  </div>
</template>
<style scoped>
.componentBody {
  margin-bottom: 20px;
}

/* 左滑 */
.goods-card {
  margin: 0;
  background-color: @white;
}

.delete-button {
  height: 100%;
}
</style>
<script>
import user from "./user";
import swipeCell from "../../template/swipeCell"; // 左右滑动

export default {
  components: {
    user,
    swipeCell
  },
  props: {
    titleP: { default: "用户信息组件" }
  },
  data() {
    return {
      activeNames: "1",
      title: "",
      componentList: [{ isTrue: true, position: 0 }]
    };
  },
  watch: {
    // 数据变化时：监听父页面library数据:此页面组件类名
    titleP(newVal) {
      this.title = newVal;
    }
  },
  mounted() {
    // 初始化监听父页面library数据:此页面组件类名
    this.title = this.titleP;
  },
  methods: {
    // 组件右划停用按钮操作
    disableComponent() {}
  }
};
</script>
