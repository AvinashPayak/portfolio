<template>
    <div>
        <div class="content flex flex-col items-start gap-5 lg:gap-10">
            <h1 class="tagline">From pixels to servers, <span class="text-[steelblue] text-[28px] lg:text-[80px]">I've got
                    you
                    covered</span>.</h1>
            <p class="text-justify">I'm your go-to person for everything from making things look
                pretty to sorting out the nitty-gritty backend stuff.</p>
            <div class="flex gap-5 items-center">
                <button class="text-[steelblue] flex items-center gap-3 relative rounded-full">
                    <div class="online rounded-full bg-[steelblue]"></div>
                    <div class="online rounded-full animate-ping absolute bg-[steelblue]"></div>Available
                </button>
                <a target="_blank" href="https://www.linkedin.com/in/avinashpayak/"><img src="../icons/linkedin.svg"></a>
            </div>
            <p class="text-[gray]">Developer with 3+ years of experience specialized in frontend and backend development</p>
        </div>
        <div class="autograph">
            <img class="z-10" src="../icons/name.svg" width="900" alt="">
        </div>
    </div>
</template>

<script setup>

</script>

<style scoped>
.autograph {
    grid-column: 4/7;
    grid-row: 1/1;
}

.content {
    grid-column: 1/5;
    grid-row: 1/1;
}

.tagline {
    font-weight: 800;
}

@media (width >=1024px) {
    .tagline {
        font-size: 80px;
    }

    .autograph img {
        width: 100%;
        max-width: 700px;
    }

    #hero button {
        padding: 1rem 2rem;
        border: 2px steelblue solid;
    }

    .online {
        padding: 0.5rem;
    }

    .content p {
        width: 75%;
    }

}


@media (width < 1024px) {
    .content {
        grid-area: content;
    }

    .online {
        padding: 0.5rem;
    }

    .autograph {
        display: flex;
        justify-content: center;
        grid-area: name;
    }

    .autograph img {
        width: 100%;
        max-width: 500px;
    }

    .content img {
        height: 50px;
    }

    #hero button {
        padding: 1rem;
        border: 2px steelblue solid;
    }
}</style>