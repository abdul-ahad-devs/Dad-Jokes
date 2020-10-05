<template>
    <div class="search-container">
        <form @submit.prevent="onSubmit">
            <input class="search" type="text" v-model="text" placeholder="Search Jokes..">
            <button class="back-btn" type="submit" value="Search">Search</button>
        </form>
    </div>    
</template>

<script>
export default {
    name: 'SearchJokes',
    data() {
        return {
            text: ''
        }
    },

    methods: {
        onSubmit(){
            this.$emit('search-text', this.text);
            this.text = "";
        }
    }
}
</script>

<style >
input {
    color: black;
}
.search-container {
    text-align: center;
    padding: 20px;
}
.back-btn {
    background-color: red;
    color: white;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
}

.back-btn:hover {
    cursor: pointer;
    background: white;
    color: black;
    font-weight: bold;
    border-radius: 5px;
}
.search {
    font-size: 20px;
}
</style>