<template>
  <div id="app-container" class="app-container">
    <div id="Header">
      <Header />
    </div>
    <div id="IntroIfo">
      <IntroIfo />
    </div>
    <div id="">
      <Skills />
    </div>
    <div id="AboutMe">
      <AboutMe />
    </div>
    <div id="Experiencs">
      <Experiencs />
    </div>
    <div id="Project">
      <Project />
    </div>
    <div id="Contact">
      <Contact />
    </div>
    <div id="Footer">
      <Footer />
    </div>

  </div>

</template>

<script>
import Header from './components/Header.vue'
import IntroIfo from './components/IntroIfo.vue'
import AboutMe from './components/About.vue';
import Skills from './components/Skills.vue';
import Footer from './components/Footer.vue';
import Contact from './components/Contact.vue';
import Project from './components/Project.vue';
import Experiencs from './components/Experiencs.vue';

export default {
  name: 'App',
  components: {
    Header,
    IntroIfo,
    AboutMe,
    Skills,
    Footer,
    Contact,
    Project,
    Experiencs
  }
}
</script>

<style scoped>
#Header {
  position: sticky;
  top: 0;
  width: 100%;
  margin: auto;
  background-color: #000019;
}

</style>