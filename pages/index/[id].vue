<template>
     <NuxtLayout name="post">
     <h1> {{  post.heading }} </h1>
     <h3> {{ post.date }} </h3>
     <div class="clearfix">
         <img class="images" :src="post.image" alt="image" >
         <p class="content">{{ post.post }}</p>
         <pre> {{ console.log(post) }}</pre>
     </div>
    
 
</NuxtLayout>
</template>

<script>
     export default {
          data:()=> ({
               post: {},
              
          }),
          
          computed: {
               id(){
                    return this.$route.params.id;
               }
          },

          mounted(){
               this.getPost();
          },
          methods:{
               async getPost () {
                    const res = await fetch(
                         "https://api-us.storyblok.com/v2/cdn/stories/home?version=draft&token=8emvUnYASicaG7z6CdIEpAtt&cv=1702478355"
                         );
                    const data = await res.json();
                    this.post = data.story.content.body[0].columns.find(
                         item => item._uid == this.id
                         );                                     
               }
          },
     }
</script>

<style>
     .images {
          float: left;
          padding: 1rem;
     }

     .content {
          padding-top: 1rem;
     }

     .images::after {
          content: "";
          clear: both;
          display: table;
}
</style>
