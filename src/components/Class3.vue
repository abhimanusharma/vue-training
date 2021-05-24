<template>
    <div>
        <h2>Class2</h2>
        <p>{{ name }}</p>
    </div>
</template>

<script>

export default {
    props: {
        name: String,
    },
    created() {
        console.log("created");
    },
}
</script>
