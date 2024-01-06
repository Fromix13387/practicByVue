<template>
  <div class="Calc">
      <input type="text"  v-model="str"/>
      <div class="keyboard">
          <div class="numbers">
              <div @click="str+=num" v-for="num in numbers">{{num}}</div>
          </div>
          <div class="operators">
              <div @click="str+=operator" v-for="operator in operators">{{operator}}</div>
          </div>
      </div>
      <button @click="countUp()">Посчитать</button>
  </div>
</template>

<script>
export default {
  data() {
      return {
          str: '',
          numbers: [1,2,3,4,5,6,7,8,9,0],
          operators: ['+', '-', '*', '/']
      }
  },
  methods: {
      countUp() {
          try {
              this.str = (new Function('return ' + this.str))().toString()
          }
          catch (e) {
              this.str = 0
          }

      }
  }
}
</script>

<style scoped>
  .Calc {
      display: flex;
      align-items: center;
      flex-direction: column;
      gap: 10px;
      margin: auto;
      padding: 25px;
      border-radius: 5px;
      width: fit-content;
      background-color: #cece34;
      > button {
          padding: 5px;
          background-color: #57572f;
          color: white;
      }
  }
  .Calc > input {
      height: 30px;
      padding: 5px;
      font-size: 20px;
  }
  .keyboard {
      display: flex;
  }
  .numbers, .operators {
      display: flex;
      justify-content: center;
      gap: 3px;
      > div {
          cursor: pointer;
          padding: 7px 10px;
          transition: all 0.2s ease;

          background-color: rgba(141, 141, 141, 0.28);
          &:hover {
              background-color: rgba(89, 89, 89, 0.73);
          }
      }
  }
  .numbers {
      width: 100px;
      flex-wrap: wrap;
  }
  .operators {
      flex-direction: column;
  }
</style>