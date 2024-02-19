
<template>
    <div class="flex flex-col gap-4 relative">
        <h1>Experience</h1>
        <div class="flex flex-col">
            <CreatePost class="lg:w-3/4 mx-auto" />
            <div class="lg:w-3/4 mx-auto">
                <Company :company="company" v-for="company of companies" :key="company.id" />
            </div>
        </div>
    </div>
</template>
<script setup>
import Company from '../Company.vue';
import CreatePost from '../CreatePost.vue';

const companies = [
    {
        id: 1,
        name: "Yocket",
        doj: "25 April, 2022",
        dol: "Present",
        experience: "Enhanced the Yocket website, a leading online platform for higher education opportunities abroad, while also led updates and enhancements to improve functionality and user experience of Superocket, an employee-facing web application. Responsible for end to end feature development using VueJS & TailwindCSS for frontend and NodeJs & PostgresSQL for backend.",
        designation: "SDE-1",
        logo: "/public/yocket.png",
        testimonials: [
            {
                id: 1,
                name: "Bippan Kumar",
                designation: "SDE-2",
                testimonial: "I’ve had the pleasure of working closely with Avinash at Yocket, where his frontend development skills and problem-solving skills truly stood out. He has a good understanding of web development. He is now actively seeking new opportunities in web development and I believe he would be a great fit. He has a collaborative nature and commitment to delivering high-quality code."
            }
        ],
        likes: 10,
        comments: 4,
        shares: 2,
        url: 'https://yocket.com/'
    },
    {
        id: 2,
        name: "LTIMindtree",
        doj: "27 October, 2020",
        dol: "20 April, 2022",
        experience: "Created testing strategy documents, test suites, test plans and test cases for projects. Performed accessibility testing, functional testing and reported bugs in JIRA and Azure. Created automation test scripts for projects using Selenium Webdriver",
        designation: "QA Engineer",
        logo: "/public/lti.png",
        testimonials: [
            {
                id: 1,
                name: "Sruthi PG",
                designation: "Senior QA Engineer",
                testimonial: "I had the pleasure of working with Avinash Payak in multiple projects in QA testing team for LTI. He was also an integral member in the Selenium automation projects. We had to face many challenges together in the phase of tight deadlines and I was inspired by his tenacity and hardwork. He is a deeply creative person with intelligent programming and analytic skills."
            }
        ],
        likes: 300,
        comments: 14,
        shares: 7,
        url:'https://www.ltimindtree.com/'
    },
    {
        id: 3,
        name: "Fluidesigns",
        doj: "15 March, 2020",
        dol: "15 June, 2020",
        experience: "Implemented a static website for a homeopathy clinic under guidance of a senior frontend developer. Learned how to convert Adobe XD design provided by the designer into a responsive static website using HTML, CSS and Javascript.",
        designation: "Fullstack Developer Intern",
        logo: "/public/fd.png",
        testimonials: [
            {
                id: 1,
                name: "Akshay Kedare",
                designation: "Co-founder",
                testimonial: "Avinash is a fast learner with a very good work ethic. He is dedicated, good at communication and extremely resourceful. He is always looking to up skill and isn't afraid of challenges. I had a good time working with him and wish him all luck for all his future endeavours."
            }
        ],
        likes: 5,
        comments: 2,
        shares: 0,
        url:'https://www.fluidesigns.in/'
    }
]

</script>

<style scoped>
@media (width >=1024px) {
    h1 {
        color: steelblue;
    }
}

@media (width <=1024px) {
    .section-bg {
        display: none;

    }

    h1 {
        -webkit-text-stroke-width: 1px;
        -webkit-text-stroke-color: steelblue;
        color: transparent;
    }
}

hr {
    border: 1px solid lightgrey;
}
</style>