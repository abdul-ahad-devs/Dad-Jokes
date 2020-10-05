<template>
  <div class="container">
    <div class="welcome">
       <h1>Welcome to Quarantine Jokes!</h1>
    </div>
  </div>
</template>

<script>
export default {

  head() {
    return {
        title: 'Dad Jokes',
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

<style>

.welcome {
  text-align: center;
  color: white;
}
</style>
