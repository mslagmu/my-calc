<template>
  <div id="app">
    <div style="position:float">
      <div v-for="(value,i) in pile" :key="i">{{i}} : {{value}}</div>
    </div>
    <div class="screen">{{message}}</div>
    <keyboard @key="key"></keyboard>
  </div>
</template>

<script>
import keyboard from "./components/keyboard";

export default {
  name: "App",
  data() {
    return {
      message: "",
      linecompleted: false,
      pile: []
    };
  },
  components: {
    keyboard
  },
  methods: {
    key(k) {
      if (k === "C") {
        this.message = "";
        this.linecompleted = false;
        return;
      }
      if (k === "Ent") {
        this.linecompleted = true;
        //let value = parseFloat(this.message);
        //this.pile.push(value);
        return;
      }

      if (k === "+") {
        this.linecompleted = true;
        let r = this.pile.pop() + parseFloat(this.message);
        this.message = r.toString();
        return;
      }

      if (k === "-") {
        this.linecompleted = true;
        let r = this.pile.pop() - parseFloat(this.message);
        this.message = r.toString();
        return;
      }
      if (k === "*") {
        this.linecompleted = true;
        let r = this.pile.pop() * parseFloat(this.message);
        this.message = r.toString();
        return;
      }

      if (k === "/") {
        this.linecompleted = true;
        let r = this.pile.pop() / parseFloat(this.message);
        this.message = r.toString();
        return;
      }

      if (k === "+/-") {
        this.linecompleted = true;
        let r = parseFloat(this.message);
        r = -r;
        this.message = r.toString();
        return;
      }

      if (this.linecompleted) {
        let value = parseFloat(this.message);
        this.pile.push(value);
        this.message = "";
        this.linecompleted = false;
      }
      this.message = this.message + k;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.screen {
  font-size: 40px;
  height: 60px;
  border: 1px solid black;
  width: 400px;
  text-align: right;
  margin-bottom: 5px;
}
</style>
