<!-- 首页 -->
<template>
  <view class="wrap"></view>
</template>

<script>
import { mapState } from "vuex";
import * as api from "@/service/benefitCardUser/index.js";
export default {
  name: "",
  data() {
    return {
      list: [],
    };
  },
  computed: {
    ...mapState({
      store_Class: (state) => state.store_Class,
    }),
  },
  methods: {
    init() {},
    async fetchApi() {
      const { data } = await api.getFindByUserCardNo();
      this.list = data.data;
    },
  },
};
</script>
<style lang="scss" scoped>
.wrap {
}
</style>
