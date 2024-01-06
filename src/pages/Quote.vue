<template>
  <div class="Quote">
      <button @click="getQuote()">Получить цитату</button>
      <p>{{quote}}</p>
<!--      <p v-for="q of quotes" >{{q.text}}</p>-->
  </div>
</template>

<script>
export default {
    data() {
        return {
            quote: '',
            quotes: []
        }
    },
    methods: {
        async getQuote() {
            let res = await fetch('https://type.fit/api/quotes')
            res = await res.json()
            console.log(res)
            this.quote = res[Math.floor(Math.random() * res.length)].text
            this.quotes = res
        }
    }
}
</script>

<style scoped>
  .Quote {
      display: flex;
      margin: auto;
      padding: 15px;
      width: 50%;
      gap: 20px;
      flex-direction: column;
      align-items: center;

  }
  .Quote > button {
      width: fit-content;
      padding: 5px;
      background-color: #57572f;
      color: white;
      border-radius: 10px;
  }
</style>