<template>
    <div class="create-post">
        <div class="flex items-center gap-1 lg:gap-5">
            <img class="w-10 h-10 lg:w-[80px] lg:h-[80px] rounded-full" src="./icons/me.jpg">
            <p class="text-[grey]">Update your activity?</p>
            <img class="w-7 h-7 lg:w-[80px] lg:h-[80px]" src="./icons/feeling.png">
        </div>
        <hr>
        <div class="options">
            <div>
                <img class="w-5 h-5 lg:w-[50px] lg:h-[50px]" src="./icons/photo.png" alt="">
                <span class="text-[12px] lg:text-[24px]">Photo</span>
            </div>
            <div>
                <img class="w-5 h-5 lg:w-[50px] lg:h-[50px]" src="./icons/video.png" alt="">
                <span class="text-[12px] lg:text-[24px]">Video</span>
            </div>
            <div>
                <img class="w-5 h-5 lg:w-[50px] lg:h-[50px]" src="./icons/share.png" alt="">
                <span class="text-[12px] lg:text-[24px]">Share</span>
            </div>
        </div>
    </div>
</template>

<style scoped>
.create-post {
    background-color: rgb(255, 255, 255, 0.6);
    backdrop-filter: blur(2px);
    box-shadow: lightsteelblue 5px 5px 10px;
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

hr {
    border: 1px solid lightgrey;
}

.create-post p {
    width: 100%;
    height: fit-content;
    border-radius: 2rem;
    background-color: rgb(245, 244, 244);
    box-shadow: lightsteelblue 1px 1px 2px;
}

.options {
    display: flex;
    margin: 0 1rem;
}

@media (width >=1024px) {
    .create-post {
        border-radius: 2rem;
        padding: 1.5rem;
    }

    .create-post p {
        padding: 1rem;
    }

    .options {
        gap: 1rem;
    }

    .options div {
        display: flex;
        align-items: center;
        gap: 1rem;
        border-radius: 5rem;
        padding: 0 1rem;
        color: grey;
        box-shadow: lightsteelblue 2px 5px 5px;
    }
}

@media (width < 1024px) {
    .create-post {
        border-radius: 1rem;
        padding: 1rem;
    }

    .create-post p {
        padding: 0.5rem;
    }

    .options {
        gap: 1rem;
    }

    .options div {
        display: flex;
        align-items: center;
        gap: 0.25rem;
        border-radius: 5rem;
        padding: 0.5rem 0.5rem;
        box-shadow: lightsteelblue 2px 5px 5px;
        color: grey;
    }
}
</style>