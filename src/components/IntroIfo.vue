<template>
    <div class="intro-container">
        <div class="avatar">
            <img src="../assets/image.png" alt="Avatar" />
        </div>
        <h1>
            Hi, I am <span class="highlight">RIN</span>,
            <br />
            <span class="subtitle">Web Dveloper</span>
        </h1>
    </div>
</template>

<script>
export default {
    name: "IntroIfo",
};
</script>

<style scoped>
.intro-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #fff;
    text-align: center;
    padding: 50px 20px;
    margin-bottom: 55px;
}

.avatar {
    width: 200px;
    height: 200px;
    margin-bottom: 32px;
    border-radius: 50%;
    background: #3a2b6a;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    box-shadow: 0 4px 24px 0 rgba(0, 0, 0, 0.2);
}

.avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

h1 {
    font-size: 2.5rem;
    font-weight: 400;
    margin-bottom: 32px;
    line-height: 1.2;
}

.highlight {
    color: #ff6a3d;
    font-weight: 600;
}

.subtitle {
    font-size: 2rem;
    font-weight: 400;
    color: #fff;
}


.talk-btn:hover {
    background: #5548c8;
}

.dot {
    display: inline-block;
    margin-left: 8px;
    width: 10px;
    height: 10px;
    background: #fff;
    border-radius: 50%;
}

@media (max-width: 768px) {
    .intro-container {
        padding: 30px 15px;
        margin-bottom: 25px;
    }

    h1 {
        font-size: 2rem;
    }

    .subtitle {
        font-size: 1.5rem;
    }
}
</style>