<template>
  <div>
    <Row v-for="(question, index) in questionList" :key="index">
      <Col span="12">
        <span class="qustion-text">{{ question[0] }}</span>
      </Col>
      <Col span="12">
        <span class="qustion-text">{{ question[1] }}</span>
      </Col>
    </Row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questionList: [],
    };
  },
  mounted() {
    this.makeTests();
  },
  methods: {
    makeTests() {
      for (let i = 0; i < 15; i++) {
        this.questionList.push([
          this.makeQuestionText(),
          this.makeQuestionText(),
        ]);
      }
    },
    makeQuestionText() {
      return this.getRandomInt() + " × " + this.getRandomInt() + " = ";
    },
    getRandomInt() {
      const max = 99;
      const min = 10;
      return Math.floor(Math.random() * (max - min + 1) + min);
    },
  },
};
</script>

<style scoped>
.qustion-text {
  font-size: 24pt;
}
</style>
