<template>
    <div id="friends-online">
        <h2>Friends online</h2>
        <div v-for="(friend, i) in friends" :key="i">
            <span v-if="friend.online">{{ friend.name }}</span>
        </div>
    </div>
</template>

<script>
export default {
    name: "FriendsOnline",
    props: ["friends"],
    data(){
        return{
            
        }
    }
}
</script>

<style>

</style>