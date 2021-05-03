<template>
  <div>
    <Row>
      <Col span="24">{{ getDateStr() }}</Col>
    </Row>
    <br />
    <Tabs>
      <TabPane label="乘法">
        <Multiplication></Multiplication>
      </TabPane>
      <TabPane label="除法">
        <Division></Division>
      </TabPane>
    </Tabs>
  </div>
</template>

<script>
import Multiplication from "./Multiplication.vue";
import Division from "./Division.vue";

export default {
  data() {
    return {};
  },
  components: {
    Multiplication,
    Division,
  },
  methods: {
    getDateStr() {
      const now = new Date();
      return (
        now.getFullYear() +
        "年 " +
        now.getMonth() +
        "月 " +
        now.getDate() +
        "日"
      );
    },
  },
};
</script>

<style scoped></style>
