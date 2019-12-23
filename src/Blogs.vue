<template>
    <div class="blogs">
        <h2>{{ blogTitle }}</h2>
        <button @click="changeTitle">Change blog's title </button>
        <div v-for="post in posts" :key="post.id">
            <h2>{{ post.title }}</h2>
            <p><q>{{ post.body }}</q></p>
        </div>
    </div>
</template>

<script>
import axios from "axios"
export default {
    name: "Blogs",
    data(){
        return {
            blogTitle: "Blogs",
            posts: []
        }
    },
    methods:{
        changeTitle(){
            this.blogTitle = "beforeUpdate Blogs"
        }
    },
    created(){
        axios.get("https://jsonplaceholder.typicode.com/posts/")
        .then(response => {
            //console.log(response)
            this.posts = response.data
            console.log(this.posts)
        })
    }
}
</script>