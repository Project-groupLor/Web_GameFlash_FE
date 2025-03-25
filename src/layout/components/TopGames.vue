<template>
  <section class="top-games-section">
    <div class="top-games-list">
      <div class="top-game-item">
        <div class="rank">1</div>
        <div class="game-info">
          <div class="game-thumb"></div>
          <div class="game-details">
            <h3>Tank 1990</h3>
            <div class="game-stats">
              <span class="plays">👥 8,765 lượt chơi</span>
              <span class="rating">⭐ 4.5</span>
            </div>
          </div>
        </div>
        <button class="play-btn-small">Chơi</button>
      </div>
      <div class="top-game-item">
        <div class="rank">2</div>
        <div class="game-info">
          <div class="game-thumb"></div>
          <div class="game-details">
            <h3>Bomberman</h3>
            <div class="game-stats">
              <span class="plays">👥 7,654 lượt chơi</span>
              <span class="rating">⭐ 4.4</span>
            </div>
          </div>
        </div>
        <button class="play-btn-small">Chơi</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TopGames'
}
</script>

<style scoped>
.top-games-section {
  margin-bottom: 40px;
  background-color: #2a2a3a;
  border-radius: 10px;
  padding: 25px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
}

.top-games-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.top-game-item {
  display: flex;
  align-items: center;
  background-color: #323248;
  border-radius: 8px;
  padding: 10px 15px;
  transition: all 0.3s ease;
}

.top-game-item:hover {
  transform: translateX(5px);
  background-color: #3a3a5a;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}

.rank {
  font-size: 1.8rem;
  font-weight: bold;
  color: #ff6b6b;
  width: 40px;
  text-align: center;
  text-shadow: 0 0 5px rgba(255, 107, 107, 0.5);
}

.game-info {
  display: flex;
  align-items: center;
  flex-grow: 1;
  margin: 0 15px;
}

.game-thumb {
  width: 60px;
  height: 60px;
  background-color: #3a3a4a;
  border-radius: 8px;
  margin-right: 15px;
  background-image: linear-gradient(45deg, #ff6b6b 25%, transparent 25%, transparent 50%, #ff6b6b 50%, #ff6b6b 75%, transparent 75%, transparent);
  background-size: 20px 20px;
}

.game-details h3 {
  font-size: 1.1rem;
  color: #ffffff;
  margin-bottom: 5px;
}

.game-stats {
  display: flex;
  gap: 15px;
  font-size: 0.85rem;
  color: #cccccc;
}

.play-btn-small {
  background-color: #ff6b6b;
  color: #ffffff;
  border: none;
  padding: 8px 20px;
  border-radius: 20px;
  font-weight: bold;
  cursor: pointer;
}
</style>