<template>
  <view class="mbill-bill-month-group">
    <view v-for="(d, dind) in data" :key="dind">
      <view class="group-year">{{ d.year }}</view>
      <view class="group-year-item">
        <view class="group-month-items" v-for="(m, mind) in d.items" :key="mind">
          <view class="group-month-items-date">{{ m.date }}</view>
            <view class="group-month-items-item">
          <mb-b-item
            v-for="(item, index) in m.items"
            :key="index"
            :bill="item"
          />
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: "mbill-bill-month-group",
  props: {
    data: {
      type: Array,
      default: [
        /*{
          year: "2020",
          items: [
            {
              date: "1月19日 周一",
              items: [
                {
                  id: 1,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 2,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 3,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
            {
              date: "2月10日 周二",
              items: [
                {
                  id: 4,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 5,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 6,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
            {
              date: "4月10日 周三",
              items: [
                {
                  id: 7,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 8,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 9,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
          ],
        },
        {
          year: "2021",
          items: [
            {
              date: "1月19日 周一",
              items: [
                {
                  id: 10,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 11,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 12,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
            {
              date: "2月10日 周二",
              items: [
                {
                  id: 13,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 4,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 14,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
            {
              date: "4月10日 周三",
              items: [
                {
                  id: 15,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 16,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 17,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
          ],
        },
        {
          year: "2022",
          items: [
            {
              date: "1月19日 周一",
              items: [
                {
                  id: 18,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 19,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 20,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
            {
              date: "2月10日 周二",
              items: [
                {
                  id: 21,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 22,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 23,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
            {
              date: "4月10日 周三",
              items: [
                {
                  id: 24,
                  type: 0,
                  category: "奶茶",
                  icon: "/static/assets/tea.png",
                  amount: 30495.2,
                  desc: "这是备注来着",
                  time: "13:30",
                },
                {
                  id: 25,
                  type: 1,
                  category: "奶茶1",
                  icon: "/static/assets/tea.png",
                  amount: 30495.3,
                  desc: "这是备注来着1",
                  time: "13:30",
                },
                {
                  id: 26,
                  type: 1,
                  category: "奶茶2",
                  icon: "/static/assets/tea.png",
                  amount: 30495.5,
                  desc: "这是备注来着2",
                  time: "13:30",
                },
              ],
            },
          ],
        },*/
      ],
    },
  },
};
</script>

<style lang="scss" scope>
.mbill-bill-month-group {
  margin: 0 20rpx;
  .group-year {
    padding: 20rpx 40rpx;
    font-weight: bold;
  }
  .group-year-item {
    padding: 10rpx 0;
    border-radius: 26rpx;
    background: white;
    .group-month-items {
      &-date {
        padding: 20rpx 40rpx;
        color: $grey-black-text-color;
        font-weight: 600;
      }
      &-item {
        padding: 0 30rpx;
      }
    }
  }
}
</style>
