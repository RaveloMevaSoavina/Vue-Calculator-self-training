<template>
  <div class="calculator">
    <div class="display">{{result}}</div>
    <div class="btn">AC</div>
    <div class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn operator">/</div>
    <div class="btn">7</div>
    <div class="btn">8</div>
    <div class="btn">9</div>
    <div class="btn operator">X</div>
    <div class="btn">4</div>
    <div class="btn">5</div>
    <div class="btn">6</div>
    <div class="btn operator">-</div>
    <div class="btn">1</div>
    <div class="btn">2</div>
    <div class="btn">3</div>
    <div class="btn operator">+</div>
    <div class="zero btn">0</div>
    <div class="btn">.</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
    return {
      result: "0"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.calculator {
  margin: 4rem auto;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  /* border: 1px solid red; */
  width: 400px;
  font-size: 2rem;
}

.display {
  grid-column: 1/5;
  height: 5rem;
  background-color: #333;
  color: #fff;
  text-align: right;
  font-size: 3rem;
  padding-top: 1rem;
}

.btn {
  background-color: #ddd;
  border: 0.1px solid #aaa;
}

.zero {
  grid-column: 1/3;
  text-align: center;
}

.operator {
  background-color: #f69332;
}
</style>
