<template>
    <div>
        <div class="projects-container">
            <div class="projects-list">
                <h1>Projects</h1>
                <div class="h-[500px] overflow-y-auto">
                    <div @click="selectProject(project.id)" class="project p-4 hover:cursor-pointer"
                        v-for="project in projectsData" :key="project.id">
                        <h3>{{ project.name }}</h3>
                        <div>
                            <ul class="flex gap-2 flex-wrap">
                                <li class="rounded-xl border p-1 bg-[lightsteelblue] text-[steelblue]"
                                    v-for="skill in project.techstack">{{ skill }}</li>
                            </ul>
                        </div>
                    </div>
                </div>

            </div>
            <div class="project-details">
                <div class="header bg-[lightsteelblue] ">
                    <h2 class="text-[steelblue] flex items-center gap-4">{{ selectedProject.name }} <a target="_blank" :href="selectedProject.url"><img src="../icons/new-tab.svg"></a></h2>
                    <span class="text-[steelblue]">{{ selectedProject.date }}</span>
                </div>
                <div class="flex flex-col items-center p-8">
                    <div class="flex justify-center items-center">
                        <img class="project-demo" v-for="image in selectedProject.images" :src="image" />
                    </div>
                    <div>
                        <p class="text-[steelblue]">{{ selectedProject.description }}</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="projects-accordian flex flex-col gap-4">
            <h1>Projects</h1>
            <div class="shadow-lg">
                <div v-for="project in projectsData" class="border p-2">
                    <div class='w-full mx-auto'>
                        <div class='max-w-md mx-auto space-y-6'>
                            <div @click="openAccordian(project.id)" class='flex w-full justify-start gap-4'>
                                <div class='transform transition duration-300 ease-in-out'
                                    :class="{ 'rotate-90': showAccordianData, ' -translate-y-0.0': !showAccordianData }">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                        stroke-width="1.5" stroke="steelblue" class="w-6 h-6">
                                        <path stroke-linecap="round" stroke-linejoin="round"
                                            d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                                    </svg>
                                </div>
                                <div class="flex items-center justify-start text-start gap-2 min-w text-[steelblue]">
                                    <button class="text-[16px] ">{{ project.name }}</button>
                                    <span><a target="_blank" :href="project.url"><img fill="steelblue" src="../icons/new-tab.svg" alt=""/></a></span>
                                </div>
                            </div>

                            <div class="flex flex-col justify-between w-full mt-2 p-4 text-[steelblue] border-t transform transition text-justify duration-300 ease-in-out pb-40"
                                x-cloak :x-show="project.id === index" x-collapse x-collapse.duration.500ms>
                                <p class="w-full">{{ project.description }}</p>
                            </div>

                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue';


const projectsData = [
    {
        id: 1,
        name: 'Recipe Handbook',
        description: 'User can search and view recipes by categories. User can view the ingredients and the cooking instructions',
        techstack: ['HTML', 'CSS', 'JS', 'Vue'],
        date: '2022',
        images: ['recipe-1.png', 'recipe-2.png', 'recipe-3.png'],
        url: 'https://precious-selkie-499f2f.netlify.app/'
    },
    {
        id: 2,
        name: 'To do list',
        description: 'To do list application with time tracking and sorting functionalities',
        techstack: ['HTML', 'CSS', 'JS', 'Vue'],
        date: '2021',
        images: ['todo-1.png', 'todo-2.png'],
        url: 'https://monumental-zuccutto-f92273.netlify.app/'
    },
    {
        id: 3,
        name: 'Hostel Management System',
        description: 'Manage occupancy, notice board, room allocation for a hostel',
        techstack: ['HTML', 'CSS', 'JS', 'EJS', 'NodeJs', 'ExpressJs', 'MySQL'],
        date: '2019',
        images: ['hostel-2.png'],
        url: 'https://github.com/AvinashPayak/Hostel-Management-System'
    },
    {
        id: 4,
        name: 'Homeopathy Website',
        description: 'Portfolio website for homeopathy doctor',
        techstack: ['HTML', 'CSS', 'JS'],
        date: '2020',
        images: ['homo-2.png', 'homo-1.png'],
        url: 'https://avinashpayak.github.io/Homeopathy-Website/templates/index.html'
    }
]

const showAccordianData = computed(() => selectedProject.id === index.value);
const openAccordian = (value) => {
    if(index.value === value) index.value = null;
    else index.value = value;
}
const index = ref(1);
const selectedProject = computed(() => {
    return projectsData.find((project) => project.id === index.value);
});
const selectProject = (value) => {
    index.value = value;
}
</script>
<style scoped>
h2 {
    font-size: 60px;
}

h3 {
    color: steelblue;
}

@media (width >=1024px) {

    h1 {
        color: steelblue;
        font-size: 5rem;
    }

    .projects-container {
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        grid-template-rows: 1;
        column-gap: 2rem;
    }

    .projects-list {
        grid-column: 1/3;
        box-shadow: lightsteelblue 5px 5px 10px;
        border-radius: 2rem;
        padding: 1rem 0;
    }

    .project-demo {
        width: 100%;
        min-width: 200px;
        max-width: fit-content;
        max-height: 450px;
    }

    .project-details {
        grid-column: 3/7;
        box-shadow: lightsteelblue 5px 5px 10px;
        border-radius: 2rem;
    }

    .project li {
        font-size: 16px;
    }

    .header {
        border-radius: 2rem 2rem 0 0;
        padding: 2rem;
    }

    .project {
        border-top: lightsteelblue 1px solid;
    }

    .projects-accordian {
        display: none;
    }
}

@media (width < 1024px) {
    h1 {
        -webkit-text-stroke-width: 1px;
        -webkit-text-stroke-color: steelblue;
        color: transparent;
        font-size: 40px;
    }

    .projects-container {
        display: none;
        grid-template-columns: repeat(6, 1fr);
        grid-template-rows: 1;
        column-gap: 1rem;
    }
}
</style>