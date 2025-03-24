<template>
  <section class="featured-games">
    <h2 class="section-title">Game Nổi Bật</h2>
   
    <div class="games-grid">
      <template v-for="(v, i) in listGame" :key="i">
        <div class="game-card">
          <div class="game-thumbnail"></div>
          <h3>{{ v.title }}</h3>
          <p>{{ v.description }}</p>
          <button class="play-btn">Chơi Ngay</button>
        </div>
      </template>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
     listGame  : [] 
    } 
  },
  mounted() {
    this.getListGame()
  },
  methods : {
    getListGame() {
        axios
        .get("127.0.0.1:8000/api/getdata")
        if(res.status == 1) {
          this.listGame = res.data.data
        } else {
          this.listGame = nul}
    }
  },
};
</script>
<style>
</style>