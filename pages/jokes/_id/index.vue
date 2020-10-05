<template>
    <div>
        <nuxt-link to='/jokes' >
            <button class="back-btn"><h3> ↶ Back to Jokes</h3></button>
        </nuxt-link>
        <h2> {{ joke}} </h2>
        <p>JOKE ID: {{ $route.params.id}}</p>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            joke: {

            }
        }
    },

    async created() {
       const config = {    
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
            const res = await axios.get(
                `https://icanhazdadjoke.com/j/${this.$route.params.id}`
            , config);

            this.joke = res.data.joke;

            console.log('joke', this.joke);

        }
        catch (err) {
            console.log('Error', err);
        }

    },

    head() {
        return {
            title: 'Joke',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'This is an amazing application'
                }
                

            ]
        }
    }
}
</script>


<style >
* {
    color: white;
}
.back-btn {
    background: #BF0000;
    color:white;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
}

button:hover {
    cursor: pointer;
}
</style>