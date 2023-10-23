<template>
    <form action="" @submit.prevent="submitForm">
        <div>
            <label for="userId">ID:</label>
            <input id="userId" type="text" v-model="username" />
        </div>
        <div>
            <label for="password">PW:</label>
            <input id="password" type="password" v-model="password" />
        </div>
        <button type="submit">로그인</button>
    </form>
</template>

<script>
import axios from "axios";
import { ref } from "vue";

export default {
    setup() {
        // data
        const username = ref("");
        const password = ref("");

        // methods
        const submitForm = () => {
            axios
                .post("https://jsonplaceholder.typicode.com/users/", {
                    username: username.value,
                    password: password.value,
                })
                .then((res) => {
                    console.log(res);
                });
            console.log("제출됨");
        };
        // 사용 할 것들을 전부 리턴 하면, 인스턴스 내에서 사용이 가능해 진다.
        return { username, password, submitForm };
    },
    // data() {
    //     return {
    //         username: "",
    //         password: "",
    //     };
    // },
    // methods: {
    //     submitForm() {
    //         // preventDefault를 메소드에서 직접 하지 않고 form 태그에서 바로 @submit.prevent로도 할 수 있다.
    //         // event.preventDefault();
    //         axios
    //             .post("https://jsonplaceholder.typicode.com/users/", {
    //                 username: this.username,
    //                 password: this.password,
    //             })
    //             .then((res) => {
    //                 console.log(res);
    //             });
    //         console.log("제출됨");
    //     },
    // },
};
</script>

<style scoped></style>
