<template>
    <h2>My Experienc</h2>
    <div class="timeline">
        <div class="container" :class="index % 2 === 0 ? 'left' : 'right'" v-for="(item, index) in timelineItems"
            :key="index">
            <div class="date">{{ item.date }}</div>
            <i class="icon fa" :class="item.icon"></i>
            <div class="content">
                <h2>{{ item.title }}</h2>
                <p>{{ item.content }}</p>
            </div>
        </div>
    </div>


</template>

<script>
export default {
    name: "Timeline",
    data() {
        return {
            timelineItems: [
                {
                    date: "04 Dec 24",
                    icon: "fa-home",
                    title: "VIREAK BUN THAM EXPRESS",
                    content:
                        "I developed websites using HTML, CSS, JavaScript, PHP, and MySQL, creating user-friendly web applications that streamline data access. I managed databases with MySQL to ensure efficient data handling. Additionally, I developed an Android app called Buspad using Java in Android Studio, where I designed simple screens and incorporated features for real-time updates. I also conducted thorough testing to ensure the app functions seamlessly.",
                },
                {
                    date: "01 Aug 24",
                    icon: "fa-briefcase",
                    title: "Dai-ichi Life Insurance (Cambodia) Plc.",
                    content:
                        "I collaborated with a team as an Application Developer, utilizing SQL Server and Report Builder to develop reports tailored for business users. My responsibilities included supporting and maintaining Management Information Systems (MIS) to ensure optimal functionality and accessibility of data.",
                },
                {
                    date: "2023-2025",
                    icon: "fa-briefcase",
                    title: "PASSERELLES NUMÉRIQUES CAMBODIA",
                    content:
                        "Completed a comprehensive two-year program focused on information technology and web development. Gained hands-on experience in HTML, CSS, JavaScript, Vue.js, Laravel, Node.js, databases like MySQL, and participated in many project-based learning activities.Graduated in February 2025.",
                },
                {
                    date: "2022",
                    icon: "fa-briefcase",
                    title: "BANTEAY CHHMAR HIGH SCHOOL",
                    content:
                        "Graduated from Banteay Chhmar High School with a focus on science.Graduated in 2022.",
                },

            ],
        };
    }

};
</script>

<style scoped>
*,
*::before,
*::after {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
    background: #ffffff;
}

.timeline {
    position: relative;
    width: 100%;
    max-width: 1140px;
    margin: 0 auto;
    padding: 10px 0;
}

.timeline::after {
    content: '';
    position: absolute;
    width: 2px;
    background: #ff5e62;
    top: 0;
    bottom: 0;
    left: 50%;
    margin-left: -1px;
}

.container {
    padding: 15px 30px;
    position: relative;
    background: inherit;
    width: 50%;
}

.container.left {
    left: 0;
}

.container.right {
    left: 50%;
}

.container::after {
    content: '';
    position: absolute;
    width: 16px;
    height: 16px;
    top: calc(50% - 8px);
    right: -8px;
    background: #ffffff;
    border: 2px solid #ff5e62;
    border-radius: 16px;
    z-index: 1;
}

.container.right::after {
    left: -8px;
}

.container.right::before {
    left: 8px;
}

.container .date {
    position: absolute;
    display: inline-block;
    top: calc(50% - 8px);
    text-align: center;
    font-size: 14px;
    font-weight: bold;
    color: #ff5e62;
    text-transform: uppercase;
    letter-spacing: 1px;
    z-index: 1;
}

.container.left .date {
    right: -95px;
}

.container.right .date {
    left: -95px;
}


.container.left .icon {
    right: 56px;
}

.container.right .icon {
    left: 56px;
}


.container .content h2 {
    margin: 0 0 10px 0;
    font-size: 18px;
    font-weight: normal;
    color: #46caff;
}

.container .content p {
    margin: 0;
    font-size: 16px;
    line-height: 22px;
    color: #fff;
    font-family: "Nunito", sans-serif;
    text-align: start;
}

@media (max-width: 767.98px) {
    .timeline::after {
        left: 90px;
    }

    .container {
        width: 100%;
        padding-left: 120px;
        padding-right: 30px;
    }

    .container.right {
        left: 0%;
    }

    .container.left::after,
    .container.right::after {
        left: 82px;
    }

    .container.left .date,
    .container.right .date {
        right: auto;
        left: 1px;
    }

}
</style>
