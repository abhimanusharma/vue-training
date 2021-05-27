<template>
    <div>
        <h2>Class2</h2>
        <p>{{ name }}</p>
    </div>
</template>

<script>

export default {
    props: {
        name: Number,
    },
    created() {
        console.log("created");
    },
}
</script>
