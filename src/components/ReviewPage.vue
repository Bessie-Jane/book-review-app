<template>
    <v-main>   
        <!-- <div class="d-flex">
            <v-icon small 
                    colour="grey darken"
            >
                    mdi-arrow-left
            </v-icon>  
            <span class="mx-1 caption">Back</span>
        </div>  -->

        <div style="cursor: pointer" >
            <feather type='arrow-left' colour="grey darken" style="width:15px" class="mr-1" /> 
            <span>Back</span>
        </div> 
 
        <v-card-title class="justify-center">
            <h1>BOOK REVIEWS</h1>
        </v-card-title>

        <div class="d-flex align-center flex-col font-bold text-xl">
            <br>
            <h2>TITLE: {{bookInfo.booktitle}}</h2>
            <h2>AUTHOR: {{bookInfo.bookauthor}}</h2>
            <br>
        </div>
        
        <div v-for="(post, i) in myPosts" 
            :key="i"
        >
            <div>
                <p>REVEIWED BY: <span>{{post.byLine}}</span></p>
                <p>SUMMARY: <span>{{post.summary}}</span></p>
                <p>PUBLISHED: <span>{{post.publicationDate}}</span></p>
                <br>
            </div>    
        </div>
        
    </v-main>
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