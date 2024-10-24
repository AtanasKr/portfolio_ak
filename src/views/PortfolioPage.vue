<template>
    <div class="d-flex flex-column justify-content-center align-items-center pt-3">
        <h1>Portfolio</h1>
        <h2 class="text-white">Latest Projects</h2>
    </div>
    <div class="d-flex flex-column justify-content-center align-items-center full-height">
        <div class="text-center" style="max-width: 700px;">
            <div v-for="(project, index) in projects" :key="index" class="project-card mt-5">
                <img :src="project.pic" alt="Project Image" class="project-image" />
                <h3>{{ project.name }}</h3>
                <p>{{ project.description }}</p>
                <a :href="project.link" target="_blank" class="project-link">View Project</a>
            </div>
        </div>
    </div>
</template>

<script>
import projectsData from '../../data/projects.json';

export default {
    data() {
        return {
            projects: projectsData.projects
        };
    }
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

.project-card {
    margin: 20px 0;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #333;
    color: white;
}

.project-image {
    max-width: 100%;
    height: auto;
}

.project-link {
    color: #61dafb;
    text-decoration: none;
}

.project-link:hover {
    text-decoration: underline;
}
</style>