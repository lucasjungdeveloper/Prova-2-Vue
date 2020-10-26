<template>
    <div id="client">
        <h2>{{ client.name }}</h2>
        <p>{{ client.profession }}</p>
    </div>
</template>

<script>
export default {
    props: {
        client: Object,
    },
}
</script>

<style scoped>
#client {
    color: #ffc5ec;
}
</style>