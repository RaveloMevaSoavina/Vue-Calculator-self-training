<template>
  <div class="calculator">
    <div class="display">{{result || '0'}}</div>
    <div @click="clear" class="btn effacer">AC</div>
    <div @click="signer" class="btn">+/-</div>
    <div @click="pourcentage" class="btn">%</div>
    <div @click="division" class="btn operator">/</div>
    <div @click="ecrireNombre(7)" class="btn">7</div>
    <div @click="ecrireNombre(8)" class="btn">8</div>
    <div @click="ecrireNombre(9)" class="btn">9</div>
    <div @click="multiplication" class="btn operator">x</div>
    <div @click="ecrireNombre(4)" class="btn">4</div>
    <div @click="ecrireNombre(5)" class="btn">5</div>
    <div @click="ecrireNombre(6)" class="btn">6</div>
    <div @click="soustraction" class="btn operator">-</div>
    <div @click="ecrireNombre(1)" class="btn">1</div>
    <div @click="ecrireNombre(2)" class="btn">2</div>
    <div @click="ecrireNombre(3)" class="btn">3</div>
    <div @click="addition" class="btn operator">+</div>
    <div @click="ecrireNombre(0)" class="zero btn">0</div>
    <div @click="toFloat" class="btn">.</div>
    <div @click="egal" class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
    return {
      result: " ",
      opClicked: false,
      operateur: null,
      previous: null
    };
  },
  methods: {
    clear() {
      this.result = " ";
      const content = document.querySelector(".effacer");
      content.innerText = "AC";
    },
    signer() {
      this.result = -this.result;
    },
    pourcentage() {
      this.result = `${parseFloat(this.result) / 100}`;
    },
    ecrireNombre(nombre) {
      if (this.opClicked) {
        this.result = "";
        this.opClicked = false;
      }
      const content = document.querySelector(".effacer");
      content.innerText = "C";
      this.result = `${this.result}${nombre}`;
    },
    toFloat() {
      if (this.result.indexOf(".") === -1) {
        this.result = `${this.result}${"."}`;
      }
    },
    operatorIsClicked() {
      this.opClicked = true;
      this.previous = this.result;
    },
    division() {
      this.operateur = (x, y) => x / y;
      this.operatorIsClicked();
    },
    multiplication() {
      this.operateur = (x, y) => x * y;
      this.operatorIsClicked();
    },
    soustraction() {
      this.operateur = (x, y) => parseFloat(x) - parseFloat(y);
      this.operatorIsClicked();
    },
    addition() {
      this.operateur = (x, y) => parseFloat(x) + parseFloat(y);
      this.operatorIsClicked();
    },
    egal() {
      this.result = `${this.operateur(this.previous, this.result)}`;
      this.previous = null;
    }
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
  cursor: pointer;
}

.zero {
  grid-column: 1/3;
  text-align: center;
}

.operator {
  background-color: #f69332;
}
</style>
