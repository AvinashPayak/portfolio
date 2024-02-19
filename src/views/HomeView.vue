<template>
  <NavBar class="z-10 sticky top-0 bg-[lightsteelblue] bg-opacity-50 backdrop-blur-sm" />
  <main>
    <div class="contain">
      <Hero id="hero" />
      <Experience id="experience" />
      <Accolades id="accolades" />
      <Projects id="projects" />
      <Contact id="contact" />
      <button type="button" data-te-ripple-init data-te-ripple-color="light"
        class="!fixed bottom-5 right-5 hidden rounded-full bg-[steelblue] p-3 text-xs font-medium uppercase leading-tight text-white shadow-md transition duration-150 ease-in-out hover:bg-[lightsteelblue] hover:shadow-lg focus:shadow-lg focus:outline-none focus:ring-0 active:shadow-lg"
        id="btn-back-to-top">
        <svg aria-hidden="true" focusable="false" data-prefix="fas" class="h-4 w-4" role="img"
          xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
          <path fill="currentColor"
            d="M34.9 289.5l-22.2-22.2c-9.4-9.4-9.4-24.6 0-33.9L207 39c9.4-9.4 24.6-9.4 33.9 0l194.3 194.3c9.4 9.4 9.4 24.6 0 33.9L413 289.4c-9.5 9.5-25 9.3-34.3-.4L264 168.6V456c0 13.3-10.7 24-24 24h-32c-13.3 0-24-10.7-24-24V168.6L69.2 289.1c-9.3 9.8-24.8 10-34.3.4z">
          </path>
        </svg>
      </button>
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

import {
  Ripple,
  initTE,
} from "tw-elements";
import { onMounted } from 'vue';

initTE({ Ripple });



onMounted(() => {
  // Get the button
  const mybutton = document.getElementById("btn-back-to-top");

  // When the user scrolls down 20px from the top of the document, show the button

  const scrollFunction = () => {
    if (
      document.body.scrollTop > 20 ||
      document.documentElement.scrollTop > 20
    ) {
      mybutton.classList.remove("hidden");
    } else {
      mybutton.classList.add("hidden");
    }
  };
  const backToTop = () => {
    window.scrollTo({ top: 0, behavior: "smooth" });
  };

  // When the user clicks on the button, scroll to the top of the document
  mybutton.addEventListener("click", backToTop);

  window.addEventListener("scroll", scrollFunction);
})

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