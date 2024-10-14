<template>
    <nav class="navbar navbar-expand-lg">
        <div class="container-fluid">
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse justify-content-center" id="navbarSupportedContent">
                <ul class="navbar-nav mb-2 mb-lg-0">
                    <li class="nav-item">
                        <router-link to="/" class="nav-link mx-4 my-4 text-white">Home</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/about" class="nav-link mx-4 my-4 text-white">About</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/portfolio" class="nav-link mx-4 my-4 text-white">Portfolio</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/contact" class="nav-link mx-4 my-4 text-white">Contact</router-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>

</script>

<style scoped>
li:hover {
    color: white;
    text-decoration: underline;
}
</style>