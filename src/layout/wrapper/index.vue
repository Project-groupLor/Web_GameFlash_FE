<template>
  <Header></Header>
  <TopGames></TopGames>
  <div class="game-flash-wrapper">
    <router-view></router-view>
  </div>
  <Footer></Footer>
</template>

<script>
import Header from '../components/Header.vue'
import TopGames from '../components/TopGames.vue'
import Footer from '../components/Footer.vue'
export default {
  name: 'GameFlashWrapper',
  components: {
    Header,
    TopGames,
    Footer
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
  background: linear-gradient(to bottom, #1a1a2e, #16162a);
  padding: 15px 0;
  box-shadow: 0 2px 15px rgba(0, 0, 0, 0.7);
  position: sticky;
  top: 0;
  z-index: 100;
  border-bottom: 3px solid #ff6b6b;
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
  width: 60px;
  height: 60px;
  border-radius: 50%;
  margin-right: 15px;
  border: 2px solid #ff6b6b;
  box-shadow: 0 0 10px rgba(255, 107, 107, 0.5);
  transition: all 0.3s ease;
}

.logo:hover {
  transform: rotate(10deg);
  box-shadow: 0 0 15px rgba(255, 107, 107, 0.8);
}

.logo-container h1 {
  font-size: 2rem;
  color: #ff6b6b;
  text-shadow: 0 0 8px rgba(255, 107, 107, 0.5), 0 0 15px rgba(255, 107, 107, 0.3);
  font-weight: bold;
  letter-spacing: 1px;
}

.main-nav {
  background-color: #2a2a3a;
  border-radius: 30px;
  padding: 5px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.3);
}

.main-nav ul {
  display: flex;
  list-style: none;
}

.main-nav li {
  margin: 0 5px;
}

.nav-link {
  color: #ffffff;
  text-decoration: none;
  font-weight: 600;
  padding: 10px 15px;
  border-radius: 20px;
  transition: all 0.3s ease;
  display: block;
  text-align: center;
  font-size: 0.95rem;
  letter-spacing: 0.5px;
}

.nav-link:hover, .nav-link.active {
  background: linear-gradient(to bottom, #ff6b6b, #ff5252);
  color: #ffffff;
  box-shadow: 0 3px 8px rgba(255, 107, 107, 0.4);
  transform: translateY(-2px);
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
  position: relative;
  overflow: hidden;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
  border: 3px solid #2a2a3a;
}

.banner::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 5px;
  background: linear-gradient(to right, #ff6b6b, #ffdd59, #ff6b6b);
  animation: rainbow 3s linear infinite;
}

@keyframes rainbow {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.banner h2 {
  font-size: 2.8rem;
  margin-bottom: 15px;
  color: #ff6b6b;
  text-shadow: 0 0 10px rgba(255, 107, 107, 0.7), 0 0 20px rgba(255, 107, 107, 0.4);
  font-weight: 800;
  letter-spacing: 1px;
  position: relative;
  display: inline-block;
}

.banner h2::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 3px;
  background-color: #ff6b6b;
  border-radius: 3px;
}

.banner p {
  font-size: 1.3rem;
  margin-bottom: 30px;
  color: #f0f0f0;
  text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.play-now-btn {
  background: linear-gradient(to bottom, #ff6b6b, #ff5252);
  color: #ffffff;
  border: none;
  padding: 15px 35px;
  font-size: 1.2rem;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: bold;
  box-shadow: 0 5px 15px rgba(255, 107, 107, 0.5), 0 0 5px rgba(255, 107, 107, 0.3);
  position: relative;
  overflow: hidden;
  z-index: 1;
}

.play-now-btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: 0.5s;
  z-index: -1;
}

.play-now-btn:hover {
  background: linear-gradient(to bottom, #ff5252, #ff3838);
  transform: translateY(-3px) scale(1.05);
  box-shadow: 0 8px 25px rgba(255, 107, 107, 0.6), 0 0 10px rgba(255, 107, 107, 0.4);
}

.play-now-btn:hover::before {
  left: 100%;
}

/* Categories Section */
.categories-section {
  margin-bottom: 40px;
  background-color: #2a2a3a;
  border-radius: 10px;
  padding: 25px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
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
  margin-top: 20px;
}

.category-card {
  background: linear-gradient(to bottom, #323248, #2a2a3a);
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  transition: all 0.3s ease;
  cursor: pointer;
  border: 2px solid #3a3a5a;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
  position: relative;
  overflow: hidden;
}

.category-card::before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  height: 5px;
  background: linear-gradient(to right, #ff6b6b, #4a69bd);
  opacity: 0;
  transition: all 0.3s ease;
}

.category-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
  border-color: #ff6b6b;
}

.category-card:hover::before {
  opacity: 1;
}

.category-icon {
  font-size: 2.5rem;
  margin-bottom: 15px;
  background: -webkit-linear-gradient(#ff6b6b, #ffdd59);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  display: inline-block;
  transition: all 0.3s ease;
}

.category-card:hover .category-icon {
  transform: scale(1.2);
}

.category-card h3 {
  font-size: 1.1rem;
  color: #ffffff;
  position: relative;
  padding-bottom: 8px;
  transition: all 0.3s ease;
}

.category-card h3::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 2px;
  background-color: #ff6b6b;
  transition: all 0.3s ease;
}

.category-card:hover h3 {
  color: #ff6b6b;
}

.category-card:hover h3::after {
  width: 50px;
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

/* Top Games Section */
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
  transition: all 0.3s ease;
}

.play-btn-small:hover {
  background-color: #ff5252;
  transform: scale(1.05);
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
  border-top: 4px solid #ff6b6b;
  box-shadow: 0 -5px 15px rgba(0, 0, 0, 0.3);
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
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-bottom: 10px;
  border: 2px solid #ff6b6b;
  box-shadow: 0 0 10px rgba(255, 107, 107, 0.5);
}

.footer-logo h3 {
  font-size: 1.3rem;
  color: #ff6b6b;
  margin-bottom: 10px;
  text-shadow: 0 0 5px rgba(255, 107, 107, 0.3);
}

.footer-slogan {
  color: #cccccc;
  font-size: 0.9rem;
  font-style: italic;
  max-width: 250px;
  line-height: 1.4;
}

.footer-links h4, .footer-contact h4, .footer-categories h4 {
  font-size: 1.1rem;
  margin-bottom: 15px;
  color: #ff6b6b;
  position: relative;
  padding-bottom: 8px;
}

.footer-links h4::after, .footer-contact h4::after, .footer-categories h4::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 40px;
  height: 2px;
  background-color: #ff6b6b;
}

.footer-links ul, .footer-categories ul {
  list-style: none;
}

.footer-links li, .footer-categories li {
  margin-bottom: 10px;
  position: relative;
  padding-left: 15px;
}

.footer-links li::before, .footer-categories li::before {
  content: '➤';
  position: absolute;
  left: 0;
  color: #ff6b6b;
  font-size: 0.8rem;
}

.footer-links a, .footer-contact a, .footer-categories a, .footer-nav a {
  color: #cccccc;
  text-decoration: none;
  transition: all 0.3s ease;
}

.footer-links a:hover, .footer-contact a:hover, .footer-categories a:hover, .footer-nav a:hover {
  color: #ff6b6b;
  padding-left: 5px;
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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.social-icon:hover {
  background-color: #ff6b6b;
  color: #1a1a2e;
  transform: translateY(-3px);
  box-shadow: 0 5px 10px rgba(255, 107, 107, 0.4);
}

.footer-bottom {
  border-top: 1px solid #2a2a3a;
  padding-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}

.footer-nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
  margin-bottom: 10px;
}

.footer-nav a {
  position: relative;
}

.footer-nav a:not(:last-child)::after {
  content: '|';
  position: absolute;
  right: -12px;
  color: #444;
}

.copyright {
  text-align: center;
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