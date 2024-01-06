<template>
    <div class="header">
        <div @click="changePage(tabs.indexOf(tab))" v-for="tab in tabs">{{tab}}</div>
    </div>
</template>

<script>

export default {
   data() {
       return {
           tabs: ['Главная', 'Калькулятор', 'Генератор цитат']
       }
   },
   props: {
       changePage: {
           type: Function
       }
   }
}



</script>

<style scoped>

  .header {
      display: flex;
      justify-content: space-around;
      background-color: #2a2a2a;
      padding: 15px;
  }
  .header > * {
      font-family: Arial;
      letter-spacing: 1px;
      cursor: pointer;
      font-weight: bold;
      color: #e8e8e8;
      transition: all 0.2s ease;

  }
  .header > *:hover {
      color: #b6b6b6;
  }
</style>