<template>
  <header :class="['game-header', { 'header-hidden': isHeaderHidden }]">
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
          <li><a href="#" class="nav-link">Top Game</a></li>
          <li><a href="#" class="nav-link">Liên Hệ</a></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      lastScrollPosition: 0,
      isHeaderHidden: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  unmounted() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
      if (currentScrollPosition < 0) return
      
      if (currentScrollPosition > 100) {
        this.isHeaderHidden = currentScrollPosition > this.lastScrollPosition
      } else {
        this.isHeaderHidden = false
      }
      
      this.lastScrollPosition = currentScrollPosition
    }
  }
}
</script>

<style scoped>
.game-header {
  background-color: #1f1f2f;
  padding: 15px 0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  transition: transform 0.3s ease;
}

.header-hidden {
  transform: translateY(-100%);
}

body {
  padding-top: 80px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-container {
  display: flex;
  align-items: center;
  gap: 15px;
}

.logo {
  width: 50px;
  height: 50px;
  border-radius: 10px;
}

.logo-container h1 {
  color: #ffffff;
  font-size: 1.8rem;
  font-weight: bold;
}

.main-nav ul {
  display: flex;
  gap: 25px;
  list-style: none;
}

.nav-link {
  color: #cccccc;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
  padding: 5px 10px;
  border-radius: 5px;
}

.nav-link:hover,
.nav-link.active {
  color: #ff6b6b;
  background-color: rgba(255, 107, 107, 0.1);
}

@media (max-width: 768px) {
  .container {
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
}

@media (max-width: 480px) {
  .logo-container h1 {
    font-size: 1.5rem;
  }
}
</style>