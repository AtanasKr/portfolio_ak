<template>
    <div class="custom-border-top d-flex flex-column align-items-center">
        <h2>Follow Me</h2>
        <p style="color: gray;">Let's be social!</p>
        <div class="d-flex gap-2">
            <img class="small-icon" src="../assets/facebook-i.png" alt="facebook-icon">
            <img class="small-icon" src="../assets/github-i.png" alt="facebook-icon">
            <img class="small-icon" src="../assets/instagram-i.png" alt="facebook-icon">
        </div>
    </div>
</template>

<script>
</script>

<style scoped>
h2 {
    font-size: 1.3em;
}

.custom-border-top {
    border-top: 3px solid white;
    padding: 10px;
    color: white;
    margin-top: 7em;
}

.small-icon {
    max-width: 25px;
    max-height: 25px;
}
</style>