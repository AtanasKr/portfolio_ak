<template>
    <div class="container d-flex justify-content-center rounded-3">
        <div class="row justify-content-center g-10">
            <div class="col-4" id="left-col">
                <span class="prev-text">This Is Me</span><br>
                <span class="name-text">Atanas Krstev</span>
            </div>
            <div class="col-4" id="right-col">
                <img class="btn-portfolio" :src="require('@/assets/btn-portfolio.png')" alt="btn-portfolio"
                    style="width: 175px; height: 60px;">
            </div>
        </div>
    </div>
    <div class="d-flex flex-column align-items-center pt-5">
        <h1>About Me</h1>
        <h2 class="text-white pt-5">Personal Details</h2>
        <p class="text-white w-50 text-center pt-2">I’ve finished my Master’s in computer and software engineering at
            Technical
            University
            Sofia. My main focus
            is programming in Javascript, Vue.js, React, Node and Laravel. I enjoy tackling challenging and mind bending
            tasks. </p>
        <img class="btn-view-full-details" :src="require('@/assets/btn-view-full-details.png')"
            alt="btn-view-full-details" style="width: 200px; height: 60px;">
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.container {
    color: white;
    background-color: #1E1E30;
    max-width: 1100px;
    padding-top: 5em;
    padding-bottom: 5em;
}

.btn-portfolio,
.btn-view-full-details {
    margin-top: 1em;
    cursor: pointer;
}

.btn-portfolio:hover,
.btn-view-full-details:hover {
    opacity: 80%;
}

.name-text {
    font-weight: bold;
    font-size: 2em;
    white-space: nowrap;
}

.prev-text {
    background: linear-gradient(180deg, rgba(203, 54, 248, 0.93) 0%, rgba(71, 132, 255, 0.47) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-weight: bold;
    font-size: 2em;
    white-space: nowrap;
}

#left-col {
    margin-right: 5.7em;
    border-left: 4px solid white;
}

#right-col {
    margin-left: 5.7em;
}

h1 {
    font-weight: bold;
    font-size: 2em;
    background: linear-gradient(180deg, rgba(203, 54, 248, 0.93) 0%, rgba(71, 132, 255, 0.47) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    position: relative;
}

h1::after {
    content: "";
    display: block;
    width: 250%;
    height: 5px;
    background: white;
    position: absolute;
    left: 50%;
    bottom: -15px;
    transform: translateX(-50%);
    z-index: -1;
    border-radius: 20px;
}
</style>