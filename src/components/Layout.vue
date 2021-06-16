<template>
  <header class="header">
    <img class="header-icon" src="/assets/book.svg" alt="book icon" />
    <h1>Top 10 books for learning about trading</h1>
  </header>

  <main>
    <div class="book-items" v-for="(book, index) in tradingBooks" :key="index">
      <div class="book-item">
        <div class="book-item-title">{{book.name}}</div>
        <div class="book-item-description">
          {{book.description}}
        </div>
        <div class="book-item-link-buy">
          <a [href]="book.linkBuy">Ir al libro</a>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import tradingBooksData from "../data/trading-books.json";
export default {
    data() {
        return {
            tradingBooks: tradingBooksData.data
        }
    },
};
</script>

<style>
.header {
  display: flex;
  justify-content: center;
  align-content: center;
  gap: 2rem;
  position: sticky;
}
.header-icon {
  width: 50px;
  height: 50px;
}

.book-items {
  margin-top: 2rem;
  display: flex;
  align-content: center;
  justify-content: center;
}
.book-item {
  display: flex;
  padding: 1rem;
  flex-direction: column;
  gap: 1rem;
  background-color: rgba(28,57,114, .2);
  width: 41rem;
  border-radius: 5px;

}
.book-item-title{
    font-size: 1.3rem;
    font-weight: bold;
}
.book-item-link-buy {
    color: #fff;
    display: flex;
    justify-content: flex-end;
    align-content: center;
    text-decoration: none;
}
</style>