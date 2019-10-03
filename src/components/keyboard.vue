<template>
  <div class="cadran">
    <button @click="bclick('1/x')">1/x</button>
    <button @click="bclick('X↔Y')">X↔Y</button>
    <button @click="bclick('+/-')">+/-</button>
    <button @click="bclick('C')">C</button>
    <button @click="bclick('7')">7</button>
    <button @click="bclick('8')">8</button>
    <button @click="bclick('9')">9</button>
    <button @click="bclick('/')">/</button>
    <button @click="bclick('4')">4</button>
    <button @click="bclick('5')">5</button>
    <button @click="bclick('6')">6</button>
    <button @click="bclick('*')">*</button>
    <button @click="bclick('1')">1</button>
    <button @click="bclick('2')">2</button>
    <button @click="bclick('3')">3</button>
    <button @click="bclick('-')">-</button>
    <button @click="bclick('0')">0</button>
    <button @click="bclick('.')">.</button>
    <button @click="bclick('Ent')">Ent</button>
    <button @click="bclick('+')">+</button>
  </div>
</template>

<script>
export default {
  name: "keyboard",
  data() {
    return {};
  },
  methods: {
    bclick(s) {
      this.$emit("key", s);
    }
  }
};
</script>

<style>
.cadran {
  border: 1px solid black;
  width: 400px;
  height: 500px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-content: space-around;
}
.cadran button {
  height: 90px;
  width: 90px;
  font-size: 40px;
  background-color: khaki;
}
</style>

