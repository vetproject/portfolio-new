<template>
  <div class="resume">
    <header>
      <h1 class="name">YOUR NAME</h1>
      <p class="contact-info">
        <span>+63 917 243 3942</span>
        <span>yourname@gmail.com</span>
      </p>
      <h2 class="job-title">Web Developer</h2>
    </header>

    <section class="about">
      <h3>About Me</h3>
      <p>
        Enthusiastic Web Developer with experience in creating user-friendly web applications and mobile solutions. Proficient in
        JavaScript frameworks like ReactJS and Vue.js, with a strong foundation in HTML, CSS, and PHP. A team player who values
        high-performance environments and is committed to continuous learning.
      </p>
    </section>

    <section class="education">
      <h3>Education</h3>
      <ul>
        <li>2013 - 2018: Bachelor of Science in Information Technology, Your University</li>
        <li>2009 - 2013: Secondary School, Your High School</li>
      </ul>
    </section>

    <section class="skills">
      <h3>Skills</h3>
      <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
        <li>ReactJS</li>
        <li>Vue.js</li>
        <li>PHP</li>
        <li>MySQL</li>
      </ul>
    </section>

    <section class="experience">
      <h3>Experience</h3>
      <p>Web Developer, Dec 2014 - Present</p>
      <ul>
        <li>Developed and maintained web applications using modern frameworks.</li>
        <li>Collaborated with developers and designers to create responsive web interfaces.</li>
        <li>Implemented features in an Android app "Budget" using Android Studio, focusing on user experience and performance.</li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "Resume"
};
</script>

<style scoped>
.resume {
  font-family: Arial, sans-serif;
  margin: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #f9f9f9;
}

header {
  text-align: center;
}

.name {
  font-size: 2em;
  color: #333;
}

.contact-info {
  font-size: 0.9em;
  color: #666;
}

.job-title {
  font-size: 1.5em;
  color: #007BFF;
}

section {
  margin: 20px 0;
}

h3 {
  border-bottom: 2px solid #007BFF;
  padding-bottom: 5px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin: 5px 0;
}
</style>