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
      for (let i = 0; i < 14; i++) {
        this.questionList.push([
          this.makeQuestionText(),
          this.makeQuestionText(),
        ]);
      }
      this.questionList.push([
        this.makeQuestionText(2),
        this.makeQuestionText(2),
      ]);
    },
    makeQuestionText(divider) {
      if (divider === 2) {
        return (
          this.getRandomInt(100, 999) +
          " ÷ " +
          this.getRandomInt(11, 15) +
          " = "
        );
      }
      return (
        this.getRandomInt(100, 999) + " ÷ " + this.getRandomInt(2, 10) + " = "
      );
    },
    getRandomInt(min, max) {
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
