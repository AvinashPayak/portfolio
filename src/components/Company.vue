<template>
    <div class="company">
        <div class="flex flex-col lg:flex-row justify-between lg:items-center gap-2 lg:gap-5">
            <div class="flex gap-4 items-center">
                <img class="w-10 h-10 lg:w-[80px] lg:h-[80px] rounded-full" :src="company.logo">
                <div class="flex flex-col">
                    <p class="lg:text-[24px] flex items-center gap-2">{{ company.name }} <a target="_blank" v-if="company.url" :href="company.url"><img src="./icons/new-tab.svg" alt=""></a></p>
                    <span class="text-[gray] text-[12px] lg:text-[20px] text-[steelblue]">@{{ company.designation }}</span>
                </div>
            </div>
            <p class="text-[gray] text-[12px] lg:text-[20px]">{{ company.doj }} - {{ company.dol }}</p>
        </div>
        <hr>
        <div class="post">
            <p class="text-justify">
                {{ company.experience }}
            </p>
        </div>
        <hr>
        <div class="comments">
            <div class="comment-options">
                <img class="w-8 h-8 lg:w-[50px] lg:h-[50px]" src="./icons/heart.png">
                <span>{{ company.likes }}</span>
                <img class="w-8 h-8 lg:w-[50px] lg:h-[50px]" src="./icons/comment.png">
                <span>{{ company.comments }}</span>
                <img class="w-8 h-8 lg:w-[50px] lg:h-[50px]" src="./icons/share.png">
                <span>{{ company.shares }}</span>
            </div>
            <div class="add-comment">
                <img class="w-10 h-10 lg:w-[80px] lg:h-[80px] rounded-full" src="./icons/me.jpg" width="90" height="90"
                    alt="">
                <div class="comment-details rounded-[32px]">
                    <p>Write a comment...</p>
                </div>
                <img class="w-8 h-8 lg:w-[50px] lg:h-[50px]" src="./icons/send.png" width="50" height="50" alt="">
            </div>
            <div v-if="company.testimonials.length" v-for="testimonial in company.testimonials" :key="testimonial.id"
                class="comment">
                <span class="profile-pic w-10 h-10 lg:w-[80px] lg:h-[80px] rounded-full">{{ testimonial.name[0] }}</span>
                <div class="comment-details flex flex-col gap-2 rounded-xl lg:rounded-3xl">
                    <div class="flex flex-col">
                        <p class="name">{{ testimonial.name }}</p>
                        <span class="text-[grey]"><span class="text-[steelblue]">@{{ testimonial.designation }}</span> at {{ company.name }}</span>
                    </div>
                    <p class="text-justify">{{ testimonial.testimonial }}</p>
                </div>
            </div>
            <div class="all-comments">
                <span>View All Comments</span>
                <span><img class="w-5 h-5 lg:w-[50px] lg:h-[50px]" src="./icons/down.png" alt=""></span>
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    company: Object
});
</script>

<style scoped>
.company {
    background-color: rgb(255, 255, 255, 0.6);
    backdrop-filter: blur(2px);
    box-shadow: lightsteelblue 5px 5px 10px;
    display: flex;
    flex-direction: column;
}

.comment,
.add-comment {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 0.5rem;
    margin: 1rem 0;
}

.comment-details {
    background-color: rgb(245, 244, 244);
    box-shadow: lightsteelblue 1px 1px 2px;
    padding: 1rem;
    width: 100%;
}

.all-comments {
    display: flex;
    justify-content: center;
    margin: 1rem 0;
    color: grey;
    align-items: center;
    gap: 0.5rem;
}

.comment-options {
    display: flex;
    align-items: center;
    gap: 1rem;
}

.profile-pic {
    color: white;
    background-color: blueviolet;
}

.name {
    font-weight: 600;
}

.add-comment {
    display: flex;
    align-items: center;
}

.add-comment img {
    border-radius: 50%;
}

@media (width >=1024px) {
    .company {
        padding: 1.5rem;
        border-radius: 2rem;
        gap: 2rem;
        margin: 2rem 0;
    }

    .profile-pic {
        color: white;
        padding: 15px 30px;
        font-size: 40px;
    }
}

@media (width < 1024px) {
    .company {
        padding: 1rem;
        border-radius: 1rem;
        gap: 1rem;
        margin: 1rem 0;
    }

    .profile-pic {
        color: white;
        padding: 8px 12px;
        font-size: 20px;
    }
}
</style>