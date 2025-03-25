<template>
  <footer class="game-footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <img src="https://cdnb.artstation.com/p/assets/images/images/006/024/065/large/anthony-beyer-anthony-beyer-logo.jpg?1495490840" alt="Game Flash Logo" class="logo">
          <p>Game Flash Tuổi Thơ - Nơi tái hiện những kí ức game tuổi thơ của bạn</p>
        </div>
        
        <div class="footer-categories">
          <h3>Danh Mục</h3>
          <ul>
            <li><a href="#">Game Hành Động</a></li>
            <li><a href="#">Game Phiêu Lưu</a></li>
            <li><a href="#">Game Đua Xe</a></li>
            <li><a href="#">Game Chiến Thuật</a></li>
          </ul>
        </div>
        
        <div class="footer-links">
          <h3>Liên Kết</h3>
          <ul>
            <li><a href="#">Về Chúng Tôi</a></li>
            <li><a href="#">Điều Khoản Sử Dụng</a></li>
            <li><a href="#">Chính Sách Bảo Mật</a></li>
            <li><a href="#">Liên Hệ</a></li>
          </ul>
        </div>
        
        <div class="footer-social">
          <h3>Theo Dõi</h3>
          <div class="social-links">
            <a href="#" class="social-link">Facebook</a>
            <a href="#" class="social-link">Twitter</a>
            <a href="#" class="social-link">Instagram</a>
            <a href="#" class="social-link">YouTube</a>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <div class="footer-nav">
          <a href="#">Trang Chủ</a>
          <a href="#">Thể Loại</a>
          <a href="#">Game Hot</a>
          <a href="#">Game Mới</a>
          <a href="#">Top Game</a>
        </div>
        <p class="copyright">© 2024 Game Flash Tuổi Thơ. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
.game-footer {
  background-color: #1f1f2f;
  padding: 60px 0 30px;
  color: #ffffff;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 40px;
  margin-bottom: 40px;
}

.footer-logo img {
  width: 80px;
  height: 80px;
  border-radius: 10px;
  margin-bottom: 15px;
}

.footer-logo p {
  color: #cccccc;
  font-size: 0.9rem;
  line-height: 1.5;
}

.footer-categories h3,
.footer-links h3,
.footer-social h3 {
  color: #ffffff;
  font-size: 1.2rem;
  margin-bottom: 20px;
}

.footer-categories ul,
.footer-links ul {
  list-style: none;
}

.footer-categories li,
.footer-links li {
  margin-bottom: 10px;
}

.footer-categories a,
.footer-links a {
  color: #cccccc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-categories a:hover,
.footer-links a:hover {
  color: #ff6b6b;
}

.social-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.social-link {
  color: #cccccc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.social-link:hover {
  color: #ff6b6b;
}

.footer-bottom {
  padding-top: 30px;
  border-top: 1px solid #2a2a3a;
  text-align: center;
}

.footer-nav {
  margin-bottom: 20px;
}

.footer-nav a {
  color: #cccccc;
  text-decoration: none;
  margin: 0 12px;
  transition: color 0.3s ease;
}

.footer-nav a:hover {
  color: #ff6b6b;
}

.copyright {
  color: #888888;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .footer-content {
    grid-template-columns: 1fr;
  }
  
  .footer-nav a {
    display: block;
    margin: 10px 0;
  }
}
</style>