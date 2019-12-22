<template>
    <div class="blogs">
        <h2>{{ blogTitle }}</h2>
        <button @click="changeTitle">Change blog's title </button>
    </div>
</template>

<script>
export default {
    name: "Blogs",
    data(){
        return {
            blogTitle: "Blogs"
        }
    },
    methods:{
        changeTitle(){
            this.blogTitle = "beforeUpdate Blogs"
        }
    }
    ,
    beforeCreate(){
        alert("Before created")
    },
    created(){
        alert("created")
    },
    beforeUpdate(){
         alert("beforeUpdate")
    }
}
</script>