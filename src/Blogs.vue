<template>
    <div class="blogs">
        <h2>{{ blogTitle }}</h2>
        <button @click="changeTitle">Change blog's title </button>
        <input type="text" v-model="searchTerm">
        <span v-if="filteredPosts.length > 0"># posts found: {{filteredPosts.length}}</span>
        <div v-for="post in filteredPosts" :key="post.id">
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
            posts: [],
            searchTerm:"",
            resultsFound: ""
        }
    },
    methods:{
        changeTitle(){
            this.blogTitle = "beforeUpdate Blogs"
        }
    },
    computed: {
        filteredPosts(){
            return this.posts.filter(post =>{
                return post.title.match(this.searchTerm)
            })
        }
    }
    ,
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