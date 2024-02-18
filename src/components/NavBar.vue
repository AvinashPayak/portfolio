<template>
    <nav class="flex items-center justify-between py-2.5 px-5">
        <div>
            <span class="logo text-[32px]">Avinash Payak</span>
        </div>
        <div class="nav-list">
            <ul class="flex gap-5 items-center">
                <li class="nav-list__item flex items-center gap-2"><a target="_blank" href="https://drive.google.com/file/d/1-Fkof3AH5h2p0mJDaLvYsd3Yed92443u/view?usp=sharing"><img src="./icons/new-tab.svg" alt=""></a>Resume</li>
            </ul>
        </div>
    </nav>
</template>

<script setup>

const listItems = [
    {
        id: 1,
        name: "Resume"
    },
    /* {
        id: 2,
        name: "Experience"
    },
    {
        id: 3,
        name: "Contact Me"
    } */
]

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=La+Belle+Aurore&display=swap');


.logo {
    font-family: "La Belle Aurore", cursive;
}
</style>