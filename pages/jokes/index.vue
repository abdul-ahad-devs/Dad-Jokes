<template>
    <div>
        <SearchJokes 
            v-on:search-text="searchText"
        />
        <Joke 
            v-for="joke in jokes" 
            :key="joke.id" 
            :id="joke.id"
            :joke="joke.joke"
        />
    </div>
</template>
<script>
import axios from "axios";
import Joke from "../../components/Joke";
import SearchJokes from "../../components/Search";

export default {

    components: {
        Joke,
        SearchJokes
    },

    data() {
        return {
            jokes: []
        }
    },

    async created() {
        const config = {    
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
            const res = await axios.get(`https://icanhazdadjoke.com/search`, config);

            this.jokes = res.data.results;

        }
        catch (err) {
            console.log('Error', err);
        }

        
    },

    methods: {
        async searchText(text) {
            const config = {    
                    headers: {
                        'Accept': 'application/json'
                    }
                }

            try {
                const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);

                this.jokes = res.data.results;

            }
            catch (err) {
                console.log('Error', err);
            }
        }
    },

    head() {
        return {
            title: 'Search Jokes',
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

</style>