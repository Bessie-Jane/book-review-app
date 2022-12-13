<template>
  <v-app>  
    <v-main class="background-picture">

      <!-- <div>
        <img src="./assets/images/LibraryImg.jpg" />    
      </div> -->

      <div class=" trans-bg"> 
        <div class="card"> 

          <div class="d-flex ml-16 mt-2" style="cursor: pointer">
            <div @click="$router.go(-1)">  
              <v-icon small color='black'>
                mdi-arrow-left
              </v-icon>  
              <span class="mx-1 caption text-black">Back</span> 
            </div>
          </div> 

          <v-progress-circular :size="20"
                              indeterminate
                              color="teal"
                              v-if="loading"
          />
          
          <div v-else>
            <review-page
                      :myPosts="posts"
                      :bookInfo="queryParams"
                      v-if="posts.length"
                      @submit="getReviews"   
            >

            </review-page>
            <h3 v-else class="font-bold card-text">NO DATA AVAILABLE YET</h3>
          </div>

          <div class="mt-2">
            <popupForm     
              @input-update="storeData"
              @submit="getReviews"  
              :load="loading"
            >
            </popupForm>
          </div>
        </div>  
      </div>  
    </v-main>
  </v-app>
</template>

<script>
import axios from 'axios';
import PopupForm from './PopupForm.vue'
import ReviewPage from './ReviewPage.vue'

export default {
  name: 'HomePage',

  data: () => {
    return {   
      posts: [],
      queryParams: {
        booktitle: '',
        bookauthor: '',
        bookisbn: '',
      },  
      loading: false
    }
  },
      
  components: {
    PopupForm,
    ReviewPage,
    // Popup,
    // Verificationemail,
  },

  methods: {
    async getReviews() {
      try {
        this.loading = true
        const title = this.queryParams.booktitle
        const author = this.queryParams.bookauthor
        const isbn = this.queryParams.bookisbn
        const apiKey= "9sPSHX9lxcPO7egmU0Buat2gVg3ecpAh"
        const url = `https://api.nytimes.com/svc/books/v3/reviews.json?api-key=${apiKey}&title=${title}&author=${author}&isbn=${isbn}`;
        const response = await axios.get(url)
        const results = response.data.results
      
        //eslint-disable-next-line no-console
        console.log(response)
          this.posts = results.map( post => ({
            publicationDate: post.publication_dt,
            byLine: post.byline,
            bookTitle: post.book_title,
            bookAuthor: post.book_author,
            summary: post.summary
          }))
        }  catch (err) {
        //eslint-disable-next-line no-console
        console.log(err.data)
      } finally {
        this.loading = false
      }
    },
  
    storeData(data) {
      this.queryParams[data.label] = data.value
    }
  },
};
</script>


<style scoped>
  .background-picture {
    background: url('../assets/images/multicolorBookPile.jpg') no-repeat center center/cover;
    /* border-radius: 25% 0 0; */
    text-align: center;
    height: 100vh;
    width: 99vw;
  }

  .trans-bg {
    background-color: rgba(0, 0, 0, 0.4);
    border-radius: 0 20% 0;
    height: 100vh;
  }

  .card {
    padding: 10% 0 0;  
    color: #000;
  }

  .card-text {
    font-size: 24px;
  }

  /* .div-img{
    background: url('./assets/images/LibraryImg-2.jpg') no-repeat center center/cover;
    background-attachment: fixed;
    background-size: cover;
    background-position: center;     
    height: 60px;
  } */

  /* .writeup {
    margin-top: 25vh; 
    width: 500px;   
    background-color: white;
  } */

  h1,p {
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  }
</style>
