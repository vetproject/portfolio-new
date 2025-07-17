<template>
    <section class="about-section">
        <div class="top">
            <div class="header">
                <div class="line"></div>
                <h4>ABOUT ME</h4>
            </div>
            <div class="right">
                <p>
                    Their versatility allows them to navigate through different components, databases, servers,
                    APIs, and more,
                    providing a comprehensive approach to building scalable, efficient, and responsive software
                    solutions.
                </p>
                <p>
                    In a rapidly evolving technological landscape, the proficiency of full-stack developers proves
                    invaluable.
                </p>
            </div>
        </div>

        <div class="down">
            <div class="left">
                <h5>Let's connect</h5>
                <div class="social-icons">
                    <a href="#"><i class="bi bi-instagram"></i></a>
                    <a href="#"><i class="bi bi-twitter"></i></a>
                    <a href="#"><i class="bi bi-facebook"></i></a>
                </div>
            </div>
            <div class="stats">
                <div class="stat-item">
                    <h3>{{ yearsExperience }}</h3>
                    <p>Years Experience</p>
                </div>
                <div class="stat-item">
                    <h3>5+</h3>
                    <p>Projects Deployed</p>
                </div>

                <div class="stat-item">
                    <h3>10+</h3>
                    <p>Success Projects</p>
                </div>
            </div>

        </div>


    </section>

</template>

<script>
export default {
    name: 'AboutMe',
    data() {
        return {
            startDate: new Date('2024-07-01') // 🛠️ Change to your actual start date
        };
    },
    computed: {
        yearsExperience() {
            const now = new Date();
            const start = this.startDate;
            const diff = now.getFullYear() - start.getFullYear();

            // Check if the current date is before the anniversary
            const monthDiff = now.getMonth() - start.getMonth();
            const dayDiff = now.getDate() - start.getDate();
            if (monthDiff < 0 || (monthDiff === 0 && dayDiff < 0)) {
                return diff - 1 + '+';
            }
            return diff + '+';
        }
    }
};
</script>


<style scoped>
@import url('https://cdn.jsdelivr.net/npm/bootstrap-icons/font/bootstrap-icons.css');

.about-section {
    margin-top: 40px;
    padding: 0px 20px;
    color: #fff;
}

.top,
.down {
    display: flex;
    margin-bottom: 20px;
    text-align: left;
    align-items: center;
}

.header {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
}

.line {
    width: 30px;
    height: 1px;
    background-color: #ccc;
    margin-right: 12px;
}

.header h4 {
    font-size: 14px;
    letter-spacing: 2px;
    color: #ccc;
    margin: 0;
}

.header,
.left {
    width: 30%;

}

.right,
.stats {
    width: 70%;
}

.left h5 {
    font-size: 18px;
    margin-bottom: 20px;
}

.social-icons {
    display: flex;
    gap: 20px;
    font-size: 20px;
}

.social-icons a {
    color: #fff;
    transition: color 0.3s ease;
}

.social-icons a:hover {
    color: #0d6efd;
}

/* Stats */
.stats {
    display: flex;
    gap: 30px;
    margin-bottom: 40px;
    flex-wrap: wrap;
}

.stat-item {
    flex: 1;
    /* min-width: 100px; */
    text-align: center;
    border-left: 1px solid #444;
    padding-left: 20px;
}

.stat-item:first-child {
    border-left: none;
    padding-left: 0;
}

.stat-item h3 {
    font-size: 28px;
    margin-bottom: 5px;
    color: #fff;
}

/* Responsive */
@media (max-width: 600px) {
    .about-section {
        margin-top: 20px;
        padding: 10px 30px;
    }

    .top,
    .down {
        flex-direction: column;
        text-align: left;
        /* margin-bottom: 10px; */
    }

    .header,
    .left,
    .right,
    .stats {
        width: 100%;
    }

    .right {
        margin: -40px;
    }

    .left {
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-wrap: wrap;
    }

    .header h4 {
        font-size: 12px;
        /* smaller header font */
    }

    .left h5 {
        font-size: 16px;
        /* adjust subheading */
    }

    .social-icons {
        justify-content: center;
        font-size: 18px;
        /* smaller icon size */
    }

    .stat-item h3 {
        font-size: 15px;
        /* reduce stat number size */
    }

    .stat-item p {
        font-size: 12px;
        /* optional: for stat labels if added */
    }

    .stat-item {
        border-left: none;
        padding-left: 0;
        padding-top: 20px;
        text-align: center;
    }

}
</style>