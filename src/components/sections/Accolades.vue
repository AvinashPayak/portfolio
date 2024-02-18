<template>
    <div>
        <div class="flex flex-col gap-5 min-w[1024px] max-w-[1360px] mx-auto">
            <h1>Accolades</h1>
            <div class="cards my-10 hidden">
                <div v-for="accolade in accoladesData" :id="accolade.cssIndex" :key="accolade.id" class="card">
                    <h2>{{ accolade.name }}</h2>
                    <p>{{ accolade.description }}</p>
                    <span class="flex items-center gap-2"><a target="_blank" v-if="accolade.url" :href="accolade.url"><img
                                src="../icons/new-tab.svg" alt=""></a> {{ accolade.time }}</span>
                </div>
            </div>
            <div class="relative lg:hidden">
                <div class="w-full">
                    <div>
                        <div class="card">
                            <h2>{{ accoladesData[index].name }}</h2>
                            <p>{{ accoladesData[index].description }}</p>
                            <span class="flex items-center gap-2"><a target="_blank" v-if="accoladesData[index].url"
                                    :href="accoladesData[index].url"><img src="../icons/new-tab.svg" alt=""></a> {{
                                        accoladesData[index].time }}</span>
                        </div>
                        <div>
                            <div @click="changeAccolade(-1)" class="absolute top-1/2 left-[-20px]">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10" viewBox="0 0 20 20"
                                    fill="steelblue">
                                    <path fill-rule="evenodd"
                                        d="M10 18a8 8 0 100-16 8 8 0 000 16zm.707-10.293a1 1 0 00-1.414-1.414l-3 3a1 1 0 000 1.414l3 3a1 1 0 001.414-1.414L9.414 11H13a1 1 0 100-2H9.414l1.293-1.293z"
                                        clip-rule="evenodd" />
                                </svg>
                            </div>
                            <div @click="changeAccolade(1)" class="absolute top-1/2 right-[-20px]">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10" viewBox="0 0 20 20"
                                    fill="steelblue">
                                    <path fill-rule="evenodd"
                                        d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-8.707l-3-3a1 1 0 00-1.414 1.414L10.586 9H7a1 1 0 100 2h3.586l-1.293 1.293a1 1 0 101.414 1.414l3-3a1 1 0 000-1.414z"
                                        clip-rule="evenodd" />
                                </svg>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const index = ref(0);
const accoladesData = [
    {
        id: 1,
        name: 'Paper Publication in IEEE Xplore',
        description: 'Automatic summarization of text and keyword extraction using Natural Language Processing to help users reduce their surfing time.',
        time: 'Published August 2020',
        cssIndex: 'publication',
        url: 'https://ieeexplore.ieee.org/document/9155852'
    },
    {
        id: 2,
        name: 'Oracle Certification',
        description: 'JAVA IoT developer Certification',
        time: 'Certified August 2018',
        cssIndex: 'oracle',
        url: 'https://drive.google.com/file/d/1H6E4gYcD1vw4oSsf3uGlf8o3pO-lDmDP/view?usp=sharing'
    },
    {
        id: 3,
        name: 'Microsoft Certification',
        description: 'Python Basics Language Certification',
        time: 'Certified July 2018',
        cssIndex: 'microsoft',
        url: 'https://www.credly.com/badges/f426e92e-eb24-4a11-963d-a33df6f8feb0/'
    },
    {
        id: 4,
        name: 'Competitive Coding',
        description: '5 star rated in hackerrank for problem solving and 1756 rated on Codechef',
        time: 'May 2021',
        cssIndex: 'cc',
        url: 'https://www.hackerrank.com/profile/avinashpayak'
    },
    {
        id: 5,
        name: 'AWS Certification',
        description: 'AWS Developer Associate DVA-C02',
        time: '(Upcoming) March 2024',
        cssIndex: 'aws'
    }
];

const changeAccolade = (value) => {
    index.value = index.value + value;
    if (index.value === -1) index.value = 4;
    else if (index.value === 5) index.value = 0;
}

</script>

<style scoped>
.card {
    border-radius: 30px;
    color: steelblue;
    background-color: rgb(255, 255, 255, 0.6);
    backdrop-filter: blur(4px);
    box-shadow: 5px 5px 20px lightsteelblue;
    display: flex;
    flex-direction: column;
    min-height: 300px;
    gap: 1rem;
}

.card span {
    margin-left: auto;
    margin-top: auto;
}

@media (width >=1024px) {

    h1 {
        -webkit-text-stroke-width: 4px;
        -webkit-text-stroke-color: lightsteelblue;
        color: transparent;
    }

    .cards {
        display: grid;
        gap: 2rem;
        justify-content: center;
        grid-template-areas:
            "pub oracle microsoft"
            "pub cc aws";
    }

    .card {
        border-radius: 30px;
        max-width: 300px;
        padding: 1.5rem;
    }

    .card p {
        font-size: 20px;
        text-align: justify;
    }

    .card span {
        font-size: 16px;
        margin-left: auto;
        margin-top: auto;
    }

    #publication {
        grid-area: pub;
        height: 100%;
    }

    #oracle {
        grid-area: oracle;
    }

    #microsoft {
        grid-area: microsoft;
    }

    #cc {
        grid-area: cc;
    }

    #aws {
        grid-area: aws;
    }
}

@media (width < 1024px) {

    h1 {
        -webkit-text-stroke-width: 1px;
        -webkit-text-stroke-color: lightsteelblue;
        color: transparent;
    }

    .cards {
        display: none;
    }

    .card span {
        font-size: 12px;
    }

    .card {
        border-radius: 30px;
        padding: 1.5rem;
    }
}</style>