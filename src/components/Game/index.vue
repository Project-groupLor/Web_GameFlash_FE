<template>
  <div class="game-container">
    <div v-if="game" class="game-details">
      <h1 class="game-title">{{ game.title }}</h1>
      <div class="game-frame-container">
        <button @click="toggleFullscreen" class="fullscreen-btn">
          <i class="fas fa-expand"></i>
        </button>
        <iframe
          :src="game.iframe_src"
          class="game-frame"
          frameborder="0"
          allowfullscreen
          ref="gameFrame"
        ></iframe>
      </div>
      <div class="game-info">
        <div class="game-stats">
          <span class="rating">⭐ {{ (Math.random() * 4 + 1).toFixed(1) }}</span>
          <span class="plays">👥 {{ Math.floor(Math.random() * 9900 + 100) }} lượt chơi</span>
        </div>
      </div>

      <!-- Game gợi ý -->
      <div class="suggested-games" v-if="suggestedGames.length">
        <h2 class="section-title">Game gợi ý</h2>
        <div class="games-grid">
          <div v-for="game in suggestedGames" :key="game.id" class="game-card" @click="$router.push(`/game/${game.id}`)">
            <div class="game-thumb" :style="{ backgroundImage: `url(${game.thumbnail})` }"></div>
            <div class="game-card-info">
              <h3>{{ game.title }}</h3>
              <div class="game-card-stats">
                <span class="plays">👥 {{ Math.floor(Math.random() * 9900 + 100) }} lượt chơi</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div v-else class="loading">
      <p>Đang tải game...</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      game: {},
      isFullscreen: false,
      suggestedGames: []
    };
  },
  mounted() {
    this.loadGame();
    document.addEventListener('fullscreenchange', this.fullscreenChangeHandler);
  },
  watch: {
    '$route.params.id': {
      handler() {
        this.loadGame();
      },
      immediate: true
    }
  },
  beforeDestroy() {
    document.removeEventListener('fullscreenchange', this.fullscreenChangeHandler);
  },
  methods: {
    async loadGame() {
      try {
        const gameId = this.$route.params.id;
        const res = await axios.get(`https://be.flash-mson.id.vn/api/getdata/${gameId}`);
        if (res.data) {
          this.game = res.data.data;
          this.loadSuggestedGames();
        } else {
          console.error('Game not found');
          this.game = null;
        }
      } catch (error) {
        console.error('Error loading game:', error);
        this.game = null;
      }
    },

    async loadSuggestedGames() {
      try {
        const res = await axios.get('https://be.flash-mson.id.vn/api/getdata');
        if (res.data && res.data.data) {
          // Lọc ra các game khác với game hiện tại và chọn ngẫu nhiên 4 game
          const otherGames = res.data.data.filter(g => g.id !== this.game.id);
          this.suggestedGames = this.getRandomGames(otherGames, 4);
        }
      } catch (error) {
        console.error('Error loading suggested games:', error);
      }
    },

    getRandomGames(games, count) {
      const shuffled = [...games].sort(() => 0.5 - Math.random());
      return shuffled.slice(0, count);
    },
    async toggleFullscreen() {
      try {
        if (!document.fullscreenElement) {
          await this.$refs.gameFrame.requestFullscreen();
        } else {
          await document.exitFullscreen();
        }
      } catch (err) {
        console.error('Error toggling fullscreen:', err);
      }
    },
    fullscreenChangeHandler() {
      this.isFullscreen = !!document.fullscreenElement;
    }
  }
};
</script>

<style scoped>
.game-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.game-title {
  color: #ff6b6b;
  text-align: center;
  margin-bottom: 20px;
}

.game-frame-container {
  position: relative;
  width: 100%;
  padding-top: 56.25%;
  background: #2a2a3a;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 8px 16px rgba(0,0,0,0.2);
}

.fullscreen-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  z-index: 10;
  background: rgba(0, 0, 0, 0.5);
  border: none;
  border-radius: 5px;
  padding: 8px;
  color: white;
  cursor: pointer;
  transition: all 0.3s ease;
}

.fullscreen-btn:hover {
  background: rgba(0, 0, 0, 0.7);
}
.game-frame {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: none;
}

.game-info {
  margin-top: 20px;
  padding: 20px;
  background: #323248;
  border-radius: 10px;
  color: #cccccc;
}

.game-description {
  margin-bottom: 15px;
  line-height: 1.6;
}

.game-stats {
  display: flex;
  justify-content: space-between;
  color: #ffd700;
}

.loading {
  text-align: center;
  padding: 50px;
  color: #cccccc;
}

.suggested-games {
  margin-top: 40px;
}

.section-title {
  color: #ff6b6b;
  margin-bottom: 20px;
  font-size: 1.5em;
}

.games-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
}

.game-card {
  background: #323248;
  border-radius: 10px;
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.game-card:hover {
  transform: translateY(-5px);
}

.game-thumb {
  width: 100%;
  height: 150px;
  background-size: cover;
  background-position: center;
  background-color: #2a2a3a;
}

.game-card-info {
  padding: 15px;
}

.game-card-info h3 {
  color: #ffffff;
  margin: 0 0 10px 0;
  font-size: 1.1em;
}

.game-card-stats {
  color: #ffd700;
  font-size: 0.9em;
}
</style>