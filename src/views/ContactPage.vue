<template>
    <div class="d-flex justify-content-center pt-3">
        <h1>Contact Me</h1>
    </div>
    <div class="form-container pt-5">
        <form>
            <div class="d-flex justify-content-center">
                <h2 class="text-white">Via email</h2>
            </div>
            <div class="form-group pt-3">
                <input type="email" class="form-control" id="exampleFormControlInput1" placeholder=" " v-model="email"
                    @focus="moveLabel('email')" @blur="resetLabel('email')">
                <label for="exampleFormControlInput1" :class="{ 'active': email || isFocused.email }">Email
                    address</label>
            </div>
            <div class="form-group pt-3">
                <textarea class="form-control" id="exampleFormControlTextarea1" rows="3" placeholder=" "
                    v-model="textarea" @focus="moveLabel('textarea')" @blur="resetLabel('textarea')"></textarea>
                <label for="exampleFormControlTextarea1"
                    :class="{ 'active': textarea || isFocused.textarea }">Message</label>
            </div>
            <div class="d-flex justify-content-center">
                <button>Send</button>
            </div>
        </form>
    </div>
    <div class="d-flex flex-column justify-content-center align-items-center pt-3">
        <div class="d-flex py-3">
            <h1 class="px-1">Or get my cv</h1><span class="pt-2">😉</span>
        </div>
        <img :src="require('@/assets/btn-get.png')" alt="btn-get" style="height: 50px; width: 100px;">
    </div>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            textarea: '',
            isFocused: {
                email: false,
                textarea: false
            }
        };
    },
    methods: {
        moveLabel(field) {
            this.isFocused[field] = true;
        },
        resetLabel(field) {
            if (this[field] === '') {
                this.isFocused[field] = false;
            }
        }
    }
}
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

h2 {
    font-size: 24px;
}

.form-container {
    display: flex;
    justify-content: center;
    align-items: center;
}

form {
    max-width: 500px;
    width: 100%;
    padding: 30px;
    margin: 10px;
    background: #1E1E30;
    border-radius: 5px;
    position: relative;
    border: 1px solid white;
}

.form-group {
    position: relative;
    margin-bottom: 20px;
}

input.form-control,
textarea.form-control {
    border: 1px solid #ccc;
    border-radius: 4px;
    padding: 10px;
    font-size: 16px;
    transition: border-color 0.2s;
    background-color: black;
    color: white;
}

input.form-control:focus,
textarea.form-control:focus {
    border-color: white;
    outline: none;
}

label {
    position: absolute;
    top: 25px;
    left: 10px;
    font-size: 16px;
    color: #aaa;
    transition: 0.2s ease all;
    pointer-events: none;
}

label.active {
    top: -10px;
    left: 10px;
    font-size: 12px;
    color: white
}

button {
    border-radius: 20px;
    color: white;
    background-color: #1E1E30;
    border-color: white;
    padding-left: 10px;
    padding-right: 10px;
}

img {
    cursor: pointer;
}

img:hover {
    opacity: 80%;
}

span {
    font-size: 20px;
}
</style>
