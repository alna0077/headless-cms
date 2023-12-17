<template>
     <header>
     <h1>
          {{ heading }}
     </h1>
</header>
</template>

<script>
     export default {
          props: ["heading"],
     };
</script>

<style>
header {
          background-color: skyblue;
          padding: 1rem;
          color: white;
     }
</style>