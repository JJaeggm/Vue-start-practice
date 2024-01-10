<template>
  <h1
    :style="styleColor"
  >{{ msg }}</h1>
  <h2
    style="color: royalblue; font-size: 40px;"
  >{{ count }}</h2>
  <button @click="increase">+1</button>
  <button @click="decrease">-1</button>
  <button @click="reset">reset</button>
  <div v-if="count > 5" class="box">
    <p>directiv box</p>
  </div>
  <ul>
    <Fruit 
    v-for="fruit of fruits" 
    :key="fruit" 
    :name="fruit">
      {{ fruit }}
    </Fruit>
  </ul>
</template>

<script>
import Fruit from './components/FruitItem.vue';
export default {
  components : {
    Fruit : Fruit
  },
  data() {
    return {
      msg : "Hello World",
      count : 0,
      fruits : ["Apple", "Orange", "Banana", "Cherry"],
      styleColor : {
        backgroundColor : 'royalblue',
      }
    }
  },
  methods : {
    increase() {
      this.count += 1
    },
    decrease() {
      this.count -= 1
    },
    reset() {
      this.count = 0
    },
  },
}
</script>

<style lang="scss">
@font-face {
    font-family: 'Pretendard-Regular';
    src: url('https://cdn.jsdelivr.net/gh/Project-Noonnu/noonfonts_2107@1.1/Pretendard-Regular.woff') format('woff');
    font-weight: 400;
    font-style: normal;
}
body {
  font-family: 'Pretendard-Regular';
}
h1 {
  font-size: 50px;
  color: orange;
}
button {
  width: 150px; height: 30px; border: none;
  border-bottom: 1px solid gray;
  background-color: transparent;
  cursor: pointer;
  &:nth-of-type(2) {
    margin: 0 10px;
  }
}
.box {
  border: 1px solid red;
  margin-top: 20px;
  p {
    font-size: 32px;
  }
}
</style>
