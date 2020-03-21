<!--
*@描述:侧边栏
*@版本:V1.0
*@作者:白爱民
*@Date:2019年12月11日20:16:26
*@最后修改人:herry
*@LastEditTime:2019年12月11日20:16:31
*@说明：-->
<template>
  <div>
    <div class="leftBody">
        <div class="titleName">

        </div>
        <div class="librarys">

        </div>
    </div>
  </div>
</template>
<style scoped>
.leftBody {
    width: 200px;
    height: 500px;
    border: 1px solid black;
    margin: 30px 10px 10px 10px;
    position: relative;
    z-index: 2;
}
</style>

<script>
export default {
  data() {
    return {
      show: false,
      value: ""
    };
  },
  mounted() {},
  methods: {
    // newitems() {
    //   var searchArr = [];
    //   if (this.searchMessage === "") {
    //   }
    // }
  }
};
</script>
