<template>
    {{errMsg}}
    <li v-for="(item, index) in posts">
        {{item.id}}
    </li>
</template>

<script>
import {defineComponent} from "vue";
import axios from "axios";

export default defineComponent({
    name: "Greet",
    data(){
        return {
            errMsg: null,
            posts: []
        }
    },
    method:{
        async getPosts() {

        }

    },
    async mounted() {
        try {
            let res = await axios.get("https://jsonplaceholder.typicode.com/users/1/posts")
            this.posts = res.data
        }catch (e) {
            this.errMsg = e
        }
    }
})
</script>

<style scoped>

</style>