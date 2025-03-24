<template>
  <div class="game-flash-wrapper">
    <!-- Header Section -->
    <header class="game-header">
      <div class="container">
        <div class="logo-container">
          <img src="https://cdnb.artstation.com/p/assets/images/images/006/024/065/large/anthony-beyer-anthony-beyer-logo.jpg?1495490840" alt="Game Flash Logo" class="logo">
          <h1>Game Flash Tuổi Thơ</h1>
        </div>
        <nav class="main-nav">
          <ul>
            <li><a href="#" class="nav-link active">Trang Chủ</a></li>
            <li><a href="#" class="nav-link">Thể Loại</a></li>
            <li><a href="#" class="nav-link">Game Hot</a></li>
            <li><a href="#" class="nav-link">Game Mới</a></li>
            <li><a href="#" class="nav-link">Liên Hệ</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <!-- Main Content Section -->
    <main class="game-content">
      <div class="container">
        <!-- Banner Section -->
        <section class="banner-section">
          <div class="banner">
            <h2>Chơi Game Flash Tuổi Thơ</h2>
            <p>Khám phá lại những trò chơi flash huyền thoại một thời</p>
            <button class="play-now-btn">Chơi Ngay</button>
          </div>
        </section>

        <!-- Game Categories -->
        <section class="categories-section">
          <h2 class="section-title">Thể Loại Game</h2>
          <div class="category-grid">
            <div class="category-card">
              <div class="category-icon">🎮</div>
              <h3>Hành Động</h3>
            </div>
            <div class="category-card">
              <div class="category-icon">🧩</div>
              <h3>Giải Đố</h3>
            </div>
            <div class="category-card">
              <div class="category-icon">🏎️</div>
              <h3>Đua Xe</h3>
            </div>
            <div class="category-card">
              <div class="category-icon">⚽</div>
              <h3>Thể Thao</h3>
            </div>
            <div class="category-card">
              <div class="category-icon">🧠</div>
              <h3>Trí Tuệ</h3>
            </div>
           
          </div>
        </section>

        <!-- Featured Games -->
        

        <!-- Router View for Dynamic Content -->
        <section class="dynamic-content">
          <slot></slot>
        </section>
      </div>
    </main>

    <!-- Footer Section -->
    <footer class="game-footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-logo">
            <img src="https://cdnb.artstation.com/p/assets/images/images/006/024/065/large/anthony-beyer-anthony-beyer-logo.jpg?1495490840" alt="Game Flash Logo" class="logo-small">
            <h3>Game Flash Tuổi Thơ</h3>
          </div>
          <div class="footer-links">
            <h4>Liên Kết</h4>
            <ul>
              <li><a href="#">Trang Chủ</a></li>
              <li><a href="#">Thể Loại</a></li>
              <li><a href="#">Game Hot</a></li>
              <li><a href="#">Game Mới</a></li>
            </ul>
          </div>
          <div class="footer-contact">
            <h4>Liên Hệ</h4>
            <p>Email: contact@gameflash.com</p>
            <p>Điện thoại: 0123-456-789</p>
            <div class="social-icons">
              <a href="#" class="social-icon">FB</a>
              <a href="#" class="social-icon">TW</a>
              <a href="#" class="social-icon">IG</a>
            </div>
          </div>
        </div>
        <div class="copyright">
          <p>&copy; 2023 Game Flash Tuổi Thơ. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'GameFlashWrapper',
  data() {
    return {
      // Data properties can be added here
    }
  },
  methods: {
    // Methods can be added here
  }
}
</script>

<style>
/* Global Styles */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #121212;
  color: #ffffff;
  line-height: 1.6;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header Styles */
.game-header {
  background-color: #1a1a2e;
  padding: 15px 0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
  position: sticky;
  top: 0;
  z-index: 100;
}

.game-header .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-right: 15px;
}

.logo-container h1 {
  font-size: 1.8rem;
  color: #ff6b6b;
  text-shadow: 0 0 5px rgba(255, 107, 107, 0.5);
}

.main-nav ul {
  display: flex;
  list-style: none;
}

.main-nav li {
  margin-left: 20px;
}

.nav-link {
  color: #ffffff;
  text-decoration: none;
  font-weight: 500;
  padding: 8px 12px;
  border-radius: 4px;
  transition: all 0.3s ease;
}

.nav-link:hover, .nav-link.active {
  background-color: #ff6b6b;
  color: #1a1a2e;
}

/* Main Content Styles */
.game-content {
  padding: 30px 0;
}

/* Banner Section */
.banner-section {
  margin-bottom: 40px;
}

.banner {
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://wallpaperaccess.com/full/7445.jpg');
  background-size: cover;
  background-position: center;
  padding: 80px 30px;
  border-radius: 10px;
  text-align: center;
  color: #ffffff;
}

.banner h2 {
  font-size: 2.5rem;
  margin-bottom: 15px;
  color: #ff6b6b;
  text-shadow: 0 0 10px rgba(255, 107, 107, 0.7);
}

.banner p {
  font-size: 1.2rem;
  margin-bottom: 25px;
}

.play-now-btn {
  background-color: #ff6b6b;
  color: #ffffff;
  border: none;
  padding: 12px 30px;
  font-size: 1.1rem;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: bold;
  box-shadow: 0 4px 15px rgba(255, 107, 107, 0.5);
}

.play-now-btn:hover {
  background-color: #ff5252;
  transform: translateY(-3px);
  box-shadow: 0 6px 20px rgba(255, 107, 107, 0.6);
}

/* Categories Section */
.categories-section {
  margin-bottom: 40px;
}

.section-title {
  font-size: 1.8rem;
  margin-bottom: 25px;
  color: #ff6b6b;
  text-align: center;
  position: relative;
  padding-bottom: 10px;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 3px;
  background-color: #ff6b6b;
}

.category-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  gap: 20px;
}

.category-card {
  background-color: #2a2a3a;
  border-radius: 8px;
  padding: 20px;
  text-align: center;
  transition: all 0.3s ease;
  cursor: pointer;
}

.category-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
  background-color: #323248;
}

.category-icon {
  font-size: 2.5rem;
  margin-bottom: 15px;
}

.category-card h3 {
  font-size: 1.1rem;
  color: #ffffff;
}

/* Featured Games */
.featured-games {
  margin-bottom: 40px;
}

.games-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 25px;
}

.game-card {
  background-color: #2a2a3a;
  border-radius: 10px;
  overflow: hidden;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.game-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
}

.game-thumbnail {
  height: 150px;
  background-color: #3a3a4a;
  background-image: linear-gradient(45deg, #ff6b6b 25%, transparent 25%, transparent 50%, #ff6b6b 50%, #ff6b6b 75%, transparent 75%, transparent);
  background-size: 20px 20px;
}

.game-card h3 {
  padding: 15px 15px 5px;
  font-size: 1.2rem;
  color: #ff6b6b;
}

.game-card p {
  padding: 0 15px 15px;
  font-size: 0.9rem;
  color: #cccccc;
  flex-grow: 1;
}

.play-btn {
  width: 100%;
  padding: 12px;
  background-color: #ff6b6b;
  color: #ffffff;
  border: none;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: auto;
}

.play-btn:hover {
  background-color: #ff5252;
}

/* Dynamic Content Section */
.dynamic-content {
  margin-top: 40px;
}

/* Footer Styles */
.game-footer {
  background-color: #1a1a2e;
  padding: 40px 0 20px;
  color: #ffffff;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 30px;
  margin-bottom: 30px;
}

.footer-logo {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.logo-small {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-bottom: 10px;
}

.footer-logo h3 {
  font-size: 1.2rem;
  color: #ff6b6b;
}

.footer-links h4, .footer-contact h4 {
  font-size: 1.1rem;
  margin-bottom: 15px;
  color: #ff6b6b;
}

.footer-links ul {
  list-style: none;
}

.footer-links li {
  margin-bottom: 10px;
}

.footer-links a, .footer-contact a {
  color: #cccccc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover, .footer-contact a:hover {
  color: #ff6b6b;
}

.footer-contact p {
  margin-bottom: 10px;
  color: #cccccc;
}

.social-icons {
  display: flex;
  gap: 15px;
  margin-top: 15px;
}

.social-icon {
  display: inline-block;
  width: 35px;
  height: 35px;
  background-color: #2a2a3a;
  border-radius: 50%;
  text-align: center;
  line-height: 35px;
  transition: all 0.3s ease;
}

.social-icon:hover {
  background-color: #ff6b6b;
  color: #1a1a2e;
}

.copyright {
  text-align: center;
  padding-top: 20px;
  border-top: 1px solid #2a2a3a;
  color: #888888;
  font-size: 0.9rem;
}

/* Responsive Styles */
@media (max-width: 768px) {
  .game-header .container {
    flex-direction: column;
  }
  
  .logo-container {
    margin-bottom: 15px;
  }
  
  .main-nav ul {
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .main-nav li {
    margin: 5px 10px;
  }
  
  .banner h2 {
    font-size: 2rem;
  }
  
  .banner p {
    font-size: 1rem;
  }
  
  .category-grid, .games-grid {
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  }
}

@media (max-width: 480px) {
  .logo-container h1 {
    font-size: 1.5rem;
  }
  
  .banner {
    padding: 50px 20px;
  }
  
  .banner h2 {
    font-size: 1.8rem;
  }
  
  .category-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .games-grid {
    grid-template-columns: 1fr;
  }
  
  .footer-content {
    grid-template-columns: 1fr;
  }
}
</style>