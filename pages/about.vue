<template>
    <div class="text-center">
        <h1>This is the about us page!</h1>
        <p>Lets do it</p>
    </div>
</template>

<script>    

export default {

    head() {
        return {
            title: 'My Application',
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
    .text-center {
        color: white;
        text-align: center;
        margin: 50px
    }
</style>