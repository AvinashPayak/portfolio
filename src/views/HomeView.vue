<template>
  <NavBar class="z-10 sticky top-0 bg-[lightsteelblue] bg-opacity-50 backdrop-blur-sm" />
  <main>
    <div class="contain">
      <Hero id="hero" />
      <Experience id="experience" />
      <Accolades id="accolades" />
      <Projects id="projects" />
      <Contact id="contact"/>
      <!-- <About id="about" /> -->
      <!-- 
      <Accolades id="accolades" /> -->
    </div>
  </main>
</template>

<script setup>
import NavBar from '@/components/NavBar.vue';
import Hero from '@/components/sections/Hero.vue';
import Experience from '@/components/sections/Experience.vue';
import Accolades from '@/components/sections/Accolades.vue';
import Projects from '@/components/sections/Projects.vue';
import Contact from '@/components/sections/Contact.vue';
//import About from '@/components/sections/About.vue';
/* 
 */

</script>

<style>
.contain {
  display: grid;
  grid-template-rows: repeat(7, fit-content);
  row-gap: 2rem;
}

.contain>div {
  width: 100%;
}

.about {
  grid-column: 1/3;
  grid-row: 3/3;
  display: grid;
  background-color: lightsteelblue;
}


#accolades {
  padding-top: 2rem;
}

@media (width >=1024px) {
  .contain {
    grid-template-columns: 1fr minmax(1024px, 1360px) 1fr;
  }

  #hero {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-column: 2/2;
  }

  #experience {
    grid-column: 2/2;
    grid-row: 3/4;
    justify-content: center;
  }

  #accolades {
    background: linear-gradient(to bottom, steelblue 70%, white 40%);
    grid-column: 1/4;
    grid-row: 4/4;
  }

  #projects {
    grid-column: 2/2;
    grid-row: 5/5;
  }

  #contact {
    grid-column: 1/4;
    grid-row: 6/6;
    background-color: black;
  }
}

@media (width < 1024px) {
  .contain {
    width: 100%;
    grid-template-columns: minmax(fit-content, 1024px);
  }

  .contain>div {
    padding: 0 2rem;
  }

  #hero {
    display: grid;
    align-items: center;
    justify-content: center;
    grid-template-areas:
      "name"
      "content";
  }

  #accolades {
    background: linear-gradient(to bottom, steelblue 50%, white 50%);
  }

  #contact {
    background-color: black;
  }
}
</style>