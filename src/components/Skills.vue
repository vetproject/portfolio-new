<template>
    <div class="skills-container">
        <h2>My Skills</h2>
        <p>Here are some of the technologies I work with:</p>
        <div class="slider-wrapper">
            <div class="skills-slider" ref="slider">
                <div class="skill-item" v-for="(skill, index) in skills" :key="index">
                    <i :class="skill.icon"></i>
                    <p>{{ skill.name }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SkillsSection',
    data() {
        return {
            skills: [
                { name: 'SQL SERVER', icon: 'bi bi-database' },
                { name: 'HTML', icon: 'devicon-html5-plain' },
                { name: 'CSS', icon: 'devicon-css3-plain' },
                { name: 'JAVASCRIPT', icon: 'devicon-javascript-plain' },
                { name: 'PHP', icon: 'devicon-php-plain' },
                { name: 'NODE.JS', icon: 'devicon-nodejs-plain' },
                { name: 'MySQL', icon: 'devicon-mysql-plain' },
                { name: 'LARAVEL', icon: 'devicon-laravel-plain' },
                { name: 'VUE.JS', icon: 'devicon-vuejs-plain' },
                { name: 'JAVA', icon: 'devicon-java-plain' },
                { name: 'REPORT BUILDER', icon: 'bi bi-bar-chart-fill' }
            ],
            scrollInterval: null
        };
    },
    mounted() {
        this.startAutoScroll();
    },
    beforeUnmount() {
        clearInterval(this.scrollInterval);
    },
    methods: {
        startAutoScroll() {
            const slider = this.$refs.slider;
            let scrollAmount = 0;
            const itemWidth = 140; // approximate width per skill item
            this.scrollInterval = setInterval(() => {
                if (slider) {
                    scrollAmount += itemWidth;
                    if (scrollAmount >= slider.scrollWidth - slider.clientWidth) {
                        scrollAmount = 0;
                    }
                    slider.scrollTo({ left: scrollAmount, behavior: 'smooth' });
                }
            }, 2000); // slide every 2 seconds
        }
    }
};
</script>

<style scoped>
@import url('https://cdn.jsdelivr.net/npm/devicon@2.15.1/devicon.min.css');
@import url('https://cdn.jsdelivr.net/npm/bootstrap-icons/font/bootstrap-icons.css');

.skills-container {
    text-align: center;
    color: white;
}


/* Slider wrapper */
.slider-wrapper {
    overflow-x: hidden;
    width: 100%;
    position: relative;
}

/* Horizontal scroll container */
.skills-slider {
    display: flex;
    flex-wrap: nowrap;
    overflow-x: auto;
    scroll-behavior: smooth;
    scrollbar-width: none;
    /* Firefox */
}

.skills-slider::-webkit-scrollbar {
    display: none;
    /* Chrome, Safari */
}

.skill-item {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    min-width: 120px;
    background: linear-gradient(90deg, #6d5dfc 0%, #46caff 100%);
    border-radius: 10px;
    margin-right: 15px;
    padding: 20px 10px;
    text-align: center;
    flex-shrink: 0;
    transition: transform 0.2s ease;
}

.skill-item:hover {
    transform: scale(1.05);
}

.skill-item i {
    font-size: 28px;
    color: #fff;
}

.skill-item p {
    margin-top: 8px;
    font-size: 14px;
    color: #fff;
}

/* Responsive */
@media (max-width: 768px) {
    .skill-item {
        min-width: 100px;
        padding: 16px 8px;
    }

    .skill-item i {
        font-size: 24px;
    }

    .skill-item p {
        font-size: 13px;
    }
}
</style>
