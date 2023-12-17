<template>
     <!-- <h1>This is my post</h1> -->
     <div class="post">
          <h2> {{  data.heading }}</h2>
          <h3> {{ data.date }}</h3>
     </div>
     
     <!-- <pre>{{ data }}</pre> -->
</template>

<script>
     export default {
          props: ["data"],
     }
</script>

<style>
.post {
  transition: all 400ms ease-out;
  cursor: pointer;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  background-color: skyblue;
  padding: 1rem;
  border-radius: 1rem;
}

.post:hover {
  transform: scale(1.05);
}
</style>