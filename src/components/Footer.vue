<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-follow">
        <h3>Follow Me</h3>
        <div class="social-icons">
          <a href="#" class="icon bi bi-facebook"></a>
          <a href="#" class="icon bi bi-instagram"></a>
          <a href="#" class="icon bi bi-twitter"></a>
        </div>
      </div>
    </div>

    <div class="footer-bottom">
      <p>&copy; 2024 <span class="brand">YOUERN Rin</span>. All rights reserved.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterSection',
}
</script>

<style scoped>
@import url('https://cdn.jsdelivr.net/npm/bootstrap-icons/font/bootstrap-icons.css');

.footer {
  color: #ddd;
  padding: 40px 20px 20px;
  text-align: center;
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
  margin-bottom: 30px;
}


.footer-follow h3 {
  font-size: 20px;
  margin-bottom: 10px;
  color: #ff5e62;
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 20px;
}

.icon {
  font-size: 26px;
  color: #bbb;
  transition: color 0.3s, transform 0.3s;
}

.icon:hover {
  color: #ff5e62;
  transform: scale(1.2);
}

.footer-bottom {
  border-top: 1px solid #444;
  padding-top: 15px;
  font-size: 14px;
  color: #888;
}

.brand {
  color: #ff5e62;
  font-weight: bold;
}

/* Responsive tweaks */
@media (max-width: 600px) {
  .footer-content {
    gap: 20px;
  }

  /* .footer-links {
    gap: 15px;
    flex-direction: column;
  } */

  .footer-follow h3 {
    font-size: 18px;
  }

  .icon {
    font-size: 14px;
  }
}
</style>
