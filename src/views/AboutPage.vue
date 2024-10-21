<template>
    <div class="container d-flex flex-column justify-content-center align-items-center pt-5">
        <h1>About Me</h1>
        <h2 class="text-white">Personal Details</h2>
    </div>

    <div class="container d-flex px-5 pt-5">
        <img :src="require('@/assets/profile-icon.png')" alt="profile-icon"
            style="width: 150px; height: 150px; margin-right:20px">
        <div class="d-flex justify-content-center align-items-center">
            <p class="text-white">I’ve finished my Master’s in computer and software engineering at Technical University
                Sofia. My main
                focus
                is programming in javascript. I enjoy tackling challenging and mind bending tasks. </p>
        </div>
    </div>

    <div class="container d-flex flex-column justify-content-center align-items-center pt-5">
        <h2 class="text-white">My Qualifications</h2>
    </div>

    <div class="container pt-5">
        <div class="row">
            <div v-for="(card, index) in cards_sm" :key="index" :class="['col-12', 'mb-4']"
                :style="{ justifyContent: index % 2 === 1 ? 'flex-end' : 'flex-start', display: 'flex' }">
                <div class="card-container pt-5">
                    <DisplayCard :content="card.content" :period="card.period" :size="card.size" />
                </div>
            </div>
        </div>
    </div>
    <div class="line" style="position: absolute; left: 50%; top:42em">
        <img :src="require('@/assets/horizontal-line.png')" alt="horizontal-line"
            style="width: 5px; height:400px; border-radius:20px;">
    </div>
    <div class="container d-flex flex-column justify-content-center align-items-center pt-5">
        <h2 class="text-white pb-5">Experience</h2>
        <div v-for="(card, index) in cards_lg" :key="index" :class="['col-12', 'mb-4']">
            <DisplayCard :content="card.content" :period="card.period" :size="card.size" :position="card.position" />
        </div>
    </div>
</template>

<script>
import DisplayCard from '../components/DisplayCard.vue'

export default {
    components: {
        DisplayCard,
    },
    data() {
        return {
            cards_sm: [
                { id: 1, content: "Diploma in Information Technology, English and Math", period: "2013-2018", size: "small" },
                { id: 2, content: "Bachelor in Computer and Software Engineering", period: "2018-2022", size: "small" },
                { id: 3, content: "Master’s in Computer and Software Engineering", period: "2022-2023", size: "small" },
            ],
            cards_lg: [
                { id: 1, content: "Auxcode Intenrship (University Internship)", position: "Android Developer", period: "1 month", size: "large" },
                { id: 2, content: "Ipsos", position: "Developer", period: "20.09.2021 - 22.04.2024", size: "large" },
                { id: 3, content: "Codix", position: "Fullstack Developer", period: "07.05.2024 - Ongoing", size: "large" }
            ]
        };
    },
};
</script>

<style scoped>
h1 {
    font-weight: bold;
    font-size: 2em;
    background: linear-gradient(180deg, rgba(203, 54, 248, 0.93) 0%, rgba(71, 132, 255, 0.47) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    position: relative;
}

.card-container {
    width: 100%;
    max-width: 500px;
}

@media (max-width: 1000px) {
    .line {
        display: none;
    }
}
</style>
