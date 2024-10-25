<template>
    <div class="d-flex flex-column justify-content-center align-items-center pt-3">
        <h1>Portfolio</h1>
        <h2 class="text-white">Latest Projects</h2>
    </div>
    <div class="d-flex flex-column justify-content-center align-items-center full-height">
        <div class="text-center" style="max-width: 700px;">
            <div v-for="(project, index) in paginatedProjects" :key="index" class="project-card mt-5">
                <img :src="getImagePath(project.pic)" alt="Project Image" class="project-image mt-3"
                    style="width: 400px; height: 300px; border-radius:20px;" />
                <h3 class="pt-3">{{ project.name }}</h3>
                <p>{{ project.description }}</p>
                <a :href="project.link" target="_blank" class="project-link">View Project</a>
            </div>
            <div class="pagination-controls pt-3">
                <button @click="prevPage" :disabled="currentPage === 1">prev</button>
                <span class='text-white'>Page {{ currentPage }} of {{ totalPages }}</span>
                <button @click="nextPage" :disabled="currentPage === totalPages">next</button>
            </div>
        </div>
    </div>
</template>

<script>
import projectsData from '../../data/projects.json';


export default {
    data() {
        return {
            projects: projectsData.projects,
            currentPage: 1,
            projectsPerPage: 3
        };
    },
    computed: {
        totalPages() {
            return Math.ceil(this.projects.length / this.projectsPerPage);
        },
        paginatedProjects() {
            const start = (this.currentPage - 1) * this.projectsPerPage;
            const end = start + this.projectsPerPage;
            return this.projects.slice(start, end);
        }
    },
    methods: {
        getImagePath(pic) {
            if (pic) {
                try {
                    console.log("Loading image:", pic);
                    return require("../assets/" + pic);
                } catch (e) {
                    console.error("Image not found:", pic);
                    return "";
                }
            } else {
                console.warn("pic is undefined or empty");
                return "";
            }
        },
        nextPage() {
            if (this.currentPage < this.totalPages) {
                this.currentPage++;
            }
        },
        prevPage() {
            if (this.currentPage > 1) {
                this.currentPage--;
            }
        }
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

.pagination-controls {
    margin-top: 20px;
}

.pagination-controls button {
    background: linear-gradient(180deg, rgba(203, 54, 248, 0.93) 0%, rgba(71, 132, 255, 0.47) 100%);
    border: none;
    color: white;
    padding: 10px 15px;
    margin: 0 5px;
    border-radius: 5px;
    cursor: pointer;
}

.pagination-controls button:disabled {
    background-color: #ccc;
    cursor: not-allowed;
}
</style>