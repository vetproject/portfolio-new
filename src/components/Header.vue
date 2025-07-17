<template>
  <header class="navbar">
    <div class="logo">
      <span>YOUERN</span><span class="logo-k">RIN</span>
    </div>
    <button class="menu-toggle" @click="menuOpen = !menuOpen" aria-label="Toggle navigation">
      <span :class="{ open: menuOpen }"></span>
      <span :class="{ open: menuOpen }"></span>
      <span :class="{ open: menuOpen }"></span>
    </button>
    <nav class="nav-links" :class="{ open: menuOpen }">
      <a href="#" :class="{ active: activeLink === 'home' }" @click="setActiveLink('home')">Home</a>
      <a href="#AboutMe" :class="{ active: activeLink === 'about' }" @click="setActiveLink('about')">About Me</a>
      <a href="#Project" :class="{ active: activeLink === 'projects' }" @click="setActiveLink('projects')">My
        Project</a>
      <a href="#Contact" :class="{ active: activeLink === 'contact' }" @click="setActiveLink('contact')">Contact</a>
      <a href="" id="hide-resp" class="download-btn" download="YOUERN_RIN.pdf">
        Download CV <span class="icon">⬇️</span>
      </a>
    </nav>
    <a href="" class="download-btn" download="YOUERN_RIN.pdf">
      Download CV <span class="icon">⬇️</span>
    </a>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      menuOpen: false,
      activeLink: 'home' // Set the default active link
    }
  },
  watch: {
    menuOpen(val) {
      if (val) {
        window.addEventListener('resize', this.handleResize);
      } else {
        window.removeEventListener('resize', this.handleResize);
      }
    }
  },
  methods: {
    handleResize() {
      if (window.innerWidth > 800) {
        this.menuOpen = false;
      }
    },
    setActiveLink(link) {
      this.activeLink = link; // Set the active link based on the clicked item
      this.menuOpen = false; // Close the menu after selection (optional)
    }
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.handleResize);
  }
}
</script>

<style scoped>
#hide-resp {
  display: none;
}

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-radius: 12px 12px 0 0;
  padding: 20px 20px;

}

.logo {
  font-size: 1.7rem;
  font-weight: 700;
  color: #fff;
  letter-spacing: 2px;
}

.logo-k {
  color: #ff5e62;
}

.menu-toggle {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 4px;
  width: 36px;
  height: 36px;
  background: none;
  border: none;
  cursor: pointer;
  z-index: 1002;
}

.menu-toggle span {
  display: block;
  height: 4px;
  width: 28px;
  background: #fff;
  border-radius: 2px;
  transition: 0.3s;
}

.menu-toggle span.open:nth-child(1) {
  transform: translateY(8px) rotate(45deg);
}

.menu-toggle span.open:nth-child(2) {
  opacity: 0;
}

.menu-toggle span.open:nth-child(3) {
  transform: translateY(-8px) rotate(-45deg);
}

.nav-links {
  display: flex;
  background: rgba(255, 255, 255, 0.06);
  border-radius: 32px;
  padding: 6px 18px;
  gap: 10px;
  transition: max-height 0.3s, opacity 0.3s;
  border: #46caff 1px solid;
}

.nav-links a {
  color: #d1d5db;
  text-decoration: none;
  font-weight: 400;
  padding: 6px 18px;
  border-radius: 24px;
  transition: background 0.2s, color 0.2s;
}

.nav-links a.active,
.nav-links a:hover {
  background: linear-gradient(90deg, #6d5dfc 0%, #46caff 100%);
  color: #fff;
}

.download-btn {
  background: linear-gradient(90deg, #6d5dfc 0%, #46caff 100%);
  color: #fff;
  padding: 10px 28px;
  border-radius: 32px;
  font-weight: 600;
  text-decoration: none;
  box-shadow: 0 4px 24px 0 rgba(109, 93, 252, 0.18);
  display: flex;
  align-items: center;
  gap: 8px;
  transition: box-shadow 0.2s, background 0.2s;
}

.download-btn:hover {
  box-shadow: 0 6px 32px 0 rgba(109, 93, 252, 0.28);
  background: linear-gradient(90deg, #46caff 0%, #6d5dfc 100%);
}

.icon {
  font-size: 1.1em;
}

/* Responsive styles */
@media screen and (max-width: 800px) {
  #hide-resp {
    display: block;
  }

  .navbar {
    flex-wrap: wrap;
    flex-direction: row;
    align-items: center;
    padding: 10px 8px;
    gap: 10px;
  }

  .logo {
    font-size: 1.2rem;
    margin-bottom: 0;
  }

  .menu-toggle {
    display: flex;
  }

  .nav-links {
    position: absolute;
    top: 60px;
    left: 0;
    right: 0;
    flex-direction: column;
    background: #000019;
    border-radius: 0 0 12px 12px;
    width: 100%;
    max-height: 0;
    opacity: 0;
    overflow: hidden;
    z-index: 1001;
    padding: 0;
    gap: 0;
    border: none;
  }

  .nav-links.open {
    max-height: 400px;
    opacity: 1;
    padding: 12px 0;
    gap: 8px;
    box-shadow: 0 8px 24px 0 rgba(0, 0, 0, 0.18);
  }

  .nav-links a {
    padding: 12px 24px;
    font-size: 1rem;
    width: 100%;
    text-align: left;
    border-radius: 0;
  }

  .download-btn {
    display: none;
  }
}
</style>