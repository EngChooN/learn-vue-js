<template>
    <h1>{{ title }}</h1>
    <button @click="changeTitle">타이틀 변경</button>
</template>

<script>
export default {
    props: ["title"],
    methods: {
        changeTitle() {
            this.$emit("change");
        },
    },
};
</script>

<style scoped></style>
