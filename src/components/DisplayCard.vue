<template>
    <div class="container d-flex flex-column justify-content-center align-items-center rounded-3 text-white py-3"
        :style="{ maxWidth: computedMaxWidth }">
        <p class="header text-center ">{{ content }}</p>
        <div class="d-flex text-center" v-if="position">
            <span>Position:</span>&nbsp;
            <p>{{ position }}</p>
        </div>
        <div class="d-flex">
            <span>Session:</span>&nbsp;
            <p>{{ period }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['content', 'period', 'size', 'position'],
    computed: {
        computedMaxWidth() {
            return this.size === 'small' ? '300px' : '550px';
        }
    }
}
</script>

<style scoped>
.container {
    background-color: #1E1E30;
}

.header {
    font-weight: 800;
}

span {
    font-weight: 500;
}
</style>