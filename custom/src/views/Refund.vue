<template>
  <div>
    <van-nav-bar
      title="退款理由"
      left-text="返回"
      left-arrow
      @click-left="$router.back(-1)"
      class="header"
    />
    <div>
      <van-cell-group>
        <van-field
          v-model="message"
          rows="5"
          autosize
          type="textarea"
          maxlength="200"
          placeholder="请输入退款理由"
          show-word-limit
        />
      </van-cell-group>
    </div>
    <div>
      <van-tabbar class="btm">
        <van-tabbar-item @click="addReason" style="font-size: 18px;color: rgb(255, 255, 255);">确定</van-tabbar-item>
      </van-tabbar>
    </div>
  </div>
</template>

<script>
import { Toast } from "vant";
export default {
  data() {
    return {
      message: ""
    };
  },
  methods: {
    addReason() {
      this.axios
        .post("/user/applyForRefund", {
          orderId: this.$route.query.id,
          comment: this.message,
          orderType: this.$route.query.type
        })
        .then(res => {
          console.log(res);
          Toast("您已成功申请退款");
          this.$router.push({
            path: "/carlist"
          });
        })
        .catch(err => {
          console.log(err);
        });
    }
  }
};
</script>

<style lang="less" scoped>
@import "../assets/css/base.less";
.btm {
  background-color: #63adde;
  color: rgb(255, 255, 255);
  font-size: 18px;
}
.van-cell {
  font-size: 16px;
}
</style>>


