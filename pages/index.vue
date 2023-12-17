<template>
     <NuxtPage v-if="id" />
     <NuxtLayout v-else>
          <Header :heading="heading" /> 
          
          <ul class="list-container">
               <li v-for="item of post">
                    <nuxt-link :to="`/${item._uid}`">
                    <post :data="item" :key="item._uid"/>
                 </nuxt-link>
                    <!-- <pre :key="item._uid"> {{ item }} </pre> -->
               </li>
          </ul>
             <!-- <pre> {{ post.length }}</pre> -->
     </NuxtLayout>
     
     <!-- <pre> {{ heading }}</pre> -->
</template>

<script>
     export default{
          data:()=>({
               post:[],
               heading:''
          }),

          computed: {
               id() {
                    return this.$route.params.id;
               }
          },

          mounted(){
               this.getPost();
          },
     
          methods:{
               async getPost () {
                    const res = await fetch("https://api-us.storyblok.com/v2/cdn/stories/home?version=draft&token=8emvUnYASicaG7z6CdIEpAtt&cv=1702305130");
                    const data = await res.json();
                    this.heading = data.story.content.Title;
                    this.post = data.story.content.body[0].columns;
               }
          }
          };
</script>

<style>
    .list-container {
  margin: 2rem;
  display: grid;
  gap: 2rem;
}
</style>