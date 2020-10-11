<template>
  <div id="app">
    <div class="news-blocks">
      <NewsBlock :news_block="news[index]" />
    </div>
  </div>
</template>

<script>
import NewsBlock from "./components/NewsBlock.vue"

export default {
  name: "App",
  components: {
    NewsBlock,
  },
  data() {
    return {
      news: [],
      index: 0,
    };
  },
  mounted: function () {
    fetch(
      "http://newsapi.org/v2/everything?q=apple&from=2020-10-10&to=2020-10-10&sortBy=popularity&apiKey=df98a1a964bd473eaabd366e7382ff9a",
      {
        method: "get",
      }
    )
      .then((response) => {
        return response.json();
      })
      .then((jsonData) => {
        this.news = jsonData.articles;
      });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.news-block {
  display: flex;
}
</style>
