<template>
  <view class="b-container x-f">
    <image class="image" mode="widthFix" :src="user.avatarUrl" />
    <view class="user-cells">
      <view class="cells">
        <view class="cell-item" v-for="(item, index) in cells" :key="index">
          <view class="cell-item-content">
            <view class="item-content x-bc">
              <text class="item-content-title">{{ item.title }}</text>
              <view class="item-content-text">
                <text class="text">{{ user[item.index] }}</text>
                <!-- <i class="iconfont icon-to right-icon" /> -->
              </view>
            </view>
            <view class="bottom-line" />
          </view>
        </view>
      </view>
    </view>
    <view class="bottom-operate" id="bottom-operate">
      <mb-ba-bottom-btn onlyone="true" @click="onBtnClick" ltext="退出登录" />
    </view>
  </view>
</template>

<script>
import { mapActions } from "vuex";

export default {
  data() {
    return {
      user: {
        avatarUrl: "/static/assets/avatar.png",
        email: "",
        gender: "未知",
        nickname: "未知",
        phone: "",
        username: "未知",
      },
      cells: [
        {
          title: "昵称",
          index: "nickname",
        },
        {
          title: "性别",
          index: "gender",
        },
        {
          title: "手机号",
          index: "phone",
        },
        {
          title: "邮箱",
          index: "email",
        },
      ],
    };
  },
  computed: {
    cacheUser() {
      // console.log(this.$store);
      return this.$store.getters.user;
    },
  },
  onShow() {},
  onLoad() {
    this.getUserDetail();
  },
  methods: {
    ...mapActions(["Logout"]),

    // 获取用户详情
    getUserDetail() {
      this.$api
        .userDetail({
          id: this.cacheUser.id,
        })
        .then((res) => {
          // console.log("列表", res);
          if (res.data.code === 0) {
            this.user = res.data.result;
          }
        });
    },

    // 退出登录
    onBtnClick(e) {
      console.log(this.user);
      this.Logout();
    },
  },
};
</script>

<style lang="scss" scope>
.image {
  background: white;
  border-radius: 50%;
  width: 160rpx;
  height: 160rpx;
  margin: 80rpx 0;
}
.user-cells {
  width: 100%;
  .cells {
    margin: 0 30rpx;
    .cell-item {
      display: flex;
      align-items: flex-start;
      font-size: 32rpx;
      padding: 30rpx 0 0 0;

      .cell-item-content {
        width: 100%;
        .item-content {
          .item-content-title {
            font-weight: bold;
          }
          width: 100%;
          margin-bottom: 30rpx;
          .item-content-text {
            display: flex;
            align-items: center;
            .text {
              margin-right: 20rpx;
            }
            .right-icon {
              color: $grey-color;
            }
          }
        }
        .bottom-line {
          height: 2rpx;
          background: $grey-light-color;
          width: 100%;
        }
      }
    }
  }
}
.bottom-operate {
  width: 100%;
  position: absolute;
  bottom: 0;
  margin-bottom: 40rpx;
}
</style>
