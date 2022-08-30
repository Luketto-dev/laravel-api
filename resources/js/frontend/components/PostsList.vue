<template>
    <main class="container pb-5">

      <div class="row ">

        <!-- creiamo una col solo per limitare la larghezza di una singola card -->
        <div class="col-6 mb-3" v-for="post in posts" :key="post.id">
          <!-- contenitore dei singoli post -->
          <div id="posts-container">
            <div class="card card-post">
              <div class="card-body">
                <div class="post_header">
                  <div class="post-meta">
                    <div class="post_title">
                      <h3>{{post.title}}</h3>
                    </div>
                    <div class="post_image">
                        <img :src="'/storage/' + post.cover_img" alt="Cover image of post 1">
                    </div>
                  </div>
                </div>
                <div class="post_text">
                  <p v-html="post.content"></p>
                </div>
              </div>
            </div>

          </div>
        </div>
      </div>
    </main>
</template>

<script>
  import axios from "axios"
export default {
    data(){
        return{
            posts: [],
        }
    },
    methods: {
      fetchPosts(){
        axios.get("/api/posts")
        .then((resp) =>{
          this.posts = resp.data;
        })
      }
    },
    mounted(){
      this.fetchPosts();
    }
}
</script>

<style>

</style>