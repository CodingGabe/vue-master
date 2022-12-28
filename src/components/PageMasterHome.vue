<template>
  <h1>Forums</h1>
  <div v-for="thread in threads" :key="thread.id">
  <!-- Title -->
    <h2>{{ thread.title }}</h2>
    <!-- Post List-->
    <div class="post-list">
        <!-- Posts -->
        <div class="posts" v-for="postId in thread.posts" :key="postId">
            <!-- User -->
            <div class="user-info">
                <a href="#" class="user-name">{{userById(postById(postId).userId).name}}</a>
                <!-- Avatar -->
                <a href="#">
                    <img :src="userById(postById(postId).userId).avatar" alt="" class="avatar">
                </a>
            </div>

            <!-- Post Content -->
            <div class="post-content">
                <p>{{postById(postId).text}}</p>
            </div>
            <!-- Publish Date -->
            <div class="post-date">
                {{postById(postId).publishedAt}}
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import sourceData from '../data.json'
export default {
    data () {
        return {
            threads: sourceData.threads,
            posts: sourceData.posts,
            users: sourceData.users
        }
    },
    methods: {
        postById (postId) {
            return this.posts.find(p => p.id === postId)
        },
        userById (userId) {
            return this.users.find(p => p.id === userId)
        } 
    }
}
</script>

<style scoped style="css">
    
</style>