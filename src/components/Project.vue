<template>
  <section class="publications">
    <h2>My Projects</h2>
    <div class="filter">
      <button @click="filter = 'all'" :class="{ active: filter === 'all' }">All</button>
      <button @click="filter = 'System'" :class="{ active: filter === 'System' }">System</button>
      <button @click="filter = 'Application'" :class="{ active: filter === 'Application' }">Application</button>
      <button @click="filter = 'Website'" :class="{ active: filter === 'Website' }">Website</button>
      <button @click="filter = 'Portfolio'" :class="{ active: filter === 'Portfolio' }">Portfolio</button>
    </div>

    <div class="cards">
      <a
        v-for="pub in filteredPublications"
        :key="pub.id"
        :href="pub.link"
        class="card card-link"
        target="_blank"
        rel="noopener noreferrer"
      >
        <img :src="pub.image" alt="Publication Image" />
        <h3>{{ pub.title }}</h3>
        <p>{{ pub.description }}</p>
        <p>
          <span
            v-for="(tech, index) in pub.lan"
            :key="index"
            class="tech-badge"
          >
            {{ tech }}
          </span>
        </p>
      </a>
    </div>
  </section>
</template>

<script>
import p1 from '../assets/images/p1.png';
import lms from '../assets/images/lms.png';
import pos from '../assets/images/pos.png'; 
import pet from '../assets/images/pet.png';
import easy from '../assets/images/easy.png';
import buspad from '../assets/images/buspad.png';
import card from '../assets/images/card.png';
import inventory from '../assets/images/inventory.png';

export default {
  data() {
    return {
      filter: 'all',
      publications: [
                {
          id: 1,
          title: 'MY FIRST PORTFOLIO',
          lan: ['PHP', 'Bootstrap', 'JavaScript'],
          type: 'Portfolio',
          description:
            'This was my first portfolio website I built in 2025. It is a simple one-pager like this one, but relied heavily on Bootstrap. Since then, I think my web development and design skills have expanded immensely.',
          image: p1,
          link: 'https://portfolio-vue-gamma.vercel.app/'
        },
        {
          id: 2,
          title: 'LMS SYSTEM',
          lan: ['PHP', 'Bootstrap', 'JavaScript', 'MySQL'],
          type: 'System',
          description:
            'A Leave Management System that allows employees to submit leave requests and managers to approve or reject them. Developed as a school project, it provided hands-on experience with real-world collaboration.',
          image: lms,
          link: 'https://github.com/So-panha/g7-lms'
        },
        {
          id: 3,
          title: 'POINT OF SALE SYSTEM',
          lan: ['HTML', 'CSS', 'JavaScript'],
          type: 'System',
          description:
            'A POS system for retail businesses to manage sales, inventory, and customer transactions. Created during a JavaScript course.',
          image: pos,
          link: '#'
        },
        {
          id: 4,
          title: 'PET STORE WEBSITE',
          lan: ['HTML', 'CSS', 'SASS'],
          type: 'Website',
          description:
            'A site for selling pets and supplies. Customers can browse, purchase, and book pet-related services.',
          image: pet,
          link: 'https://github.com/RinYouern/pet-shop-c5'
        },
        {
          id: 5,
          title: 'EASY TRAVEL',
          lan: ['Laravel', 'Bootstrap', 'Vue.js', 'MySQL'],
          type: 'Website',
          description:
            'A travel website for booking hotels, renting cars, and exploring destinations. It offers user-friendly booking and travel recommendations.',
          image: easy,
          link: 'https://github.com/RinYouern/g9-easy-travel'
        },
        {
          id: 6,
          title: 'BUSPAD',
          lan: ['Java', 'Android Studio'],
          type: 'Application',
          description:
            'Buspad is an app used on buses to watch movies, listen to music, and browse online, making travel enjoyable.',
          image: buspad,
          link: '#'
        },
        {
          id: 7,
          title: 'CARD MANAGEMENT SYSTEM',
          lan: ['PHP','BOOTSTRAP','JAVASCRIPT'],
          type: 'System',
          description:
            'A system for generating and managing digital employee cards. It allows organizations to create customizable employee ID cards, issue them securely, and validate them in real-time. Administrators can track card usage, manage employee records, and generate detailed reports.',
          image: card,
          link: 'https://github.com/rin1771/cardGenerate'
        },
        {
          id:8,
          title: 'INVENTORY MANAGEMENT SYSTEM',
          lan: ['PHP','BOOTSTRAP','JAVASCRIPT','MYSQL'],
          type: 'System',
          description:
            'An inventory management system for businesses to track stock levels, manage suppliers, and process orders. The system provides automated alerts for low stock, detailed inventory analytics, and integration with sales channels.',
          image: inventory,
          link: 'https://github.com/rin1771/IMS'
        }

      ]
    }
  },
  computed: {
    filteredPublications() {
      if (this.filter === 'all') return this.publications
      return this.publications.filter(pub => pub.type === this.filter)
    }
  }
}
</script>

<style scoped>
.publications {
  color: #ffffff;
  padding: 0 20px;
  border-radius: 12px;
}

h2 {
  text-align: center;
}

.filter {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

.filter button {
  background: none;
  border: 1px solid #46caff;
  color: #46caff;
  padding: 10px 20px;
  border-radius: 5px;
  margin: 0 5px;
  cursor: pointer;
  transition: background 0.3s, color 0.3s;
  font-family: "Coiny", system-ui;
}

.filter button.active {
  background: #46caff;
  color: #ffffff;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  border-radius: 12px;
  margin: 10px;
  width: 250px;
  transition: transform 0.3s;
  text-align: left;
  cursor: pointer;
}

.card-link {
  text-decoration: none;
  color: inherit;
  display: block;
}

.card h3 {
  margin-top: -3px;
  color: #ff5e62;
}

.card p {
  font-family: "Nunito", sans-serif;
  font-size: 10px;
  line-height: 1.5;
  margin-top: -10px;
}

.tech-badge {
  display: inline-block;
  padding: 0.25em 0.5em;
  font-size: 0.6rem;
  font-weight: 600;
  border: 1px solid #46caff;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  margin-bottom: 0.25rem;
  transition: background-color 0.3s, color 0.3s;
}

.tech-badge:hover {
  color: white;
}

.card img {
  max-width: 100%;
}

.card:hover {
  transform: scale(1.05);
}

@media screen and (max-width: 600px) {
  .filter {
    flex-wrap: wrap;
  }

  .filter button {
    margin: 5px;
    font-size: 10px;
    padding: 5px 10px;
  }
}
</style>
