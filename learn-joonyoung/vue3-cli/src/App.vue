<template>
    <AppHeader v-bind:title="msg" v-on:change="changeMessage" />
    <div>
        {{ msg }}
    </div>
    <button @click="showAlert">경고</button>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";

export default {
    components: {
        AppHeader,
    },
    data() {
        return {
            msg: "앱 헤더 컴포넌트",
        };
    },
    methods: {
        showAlert() {
            alert("hello");
        },
        changeMessage() {
            this.msg = "메세지 변경됨!";
        },
    },
};
</script>

<style scoped></style>
