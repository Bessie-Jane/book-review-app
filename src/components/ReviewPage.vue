<template>
    <div>  
        <!-- <div class="d-flex ml-16 mt-2" style="cursor: pointer">
            <v-icon small color="black">
                mdi-arrow-left
            </v-icon>  
            <span class="mx-1 caption" @click="$router.go(-1)">Back</span>
        </div>   -->
 
        <v-card-title class="justify-center font-bold text-xl">
            <h1>BOOK REVIEWS</h1>
        </v-card-title>

        <div class="d-flex align-center flex-col font-bold text-xl">
            <br>
            <h2>TITLE: {{bookInfo.booktitle}}</h2>
            <h2>AUTHOR: {{bookInfo.bookauthor}}</h2>
            <br>
        </div>
        
        <div v-for="(post, i) in myPosts" :key="i">
            <div>
                <p>REVEIWED BY: <span>{{post.byLine}}</span></p>
                <p>SUMMARY: <span>{{post.summary}}</span></p>
                <p>PUBLISHED: <span>{{post.publicationDate}}</span></p>
                <br>
            </div>    
        </div>
        
    </div>
</template>

<script>  
    export default {
        props: {
            myPosts: {
                type: Array
            },
            bookInfo: {
                type: Object
            }
        }
    }
</script>

<style>

</style>