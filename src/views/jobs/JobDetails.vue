<template>
    <h1>Job Details Page</h1>
    <div v-if="job">
    <p>The person {{ job.name }}</p>
    </div>
    <div v-else>loading</div>
</template>

<script>
export default {
    props: ['id'],
    data () {
        return {
            job: null
        }
    },
    mounted() {
        fetch("https://jsonplaceholder.typicode.com/users/" + this.id)
            .then(res => res.json())
            .then(data => this.job = data)
            .catch(err => console.log(err.message))
    }
}
</script>

<style>
</style>