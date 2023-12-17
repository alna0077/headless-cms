<template>
     <navbar />
     <div class="post-wrapper">
          <slot />
     </div>
</template>

<style>
#__nuxt {
     display: grid;     
}

h1 {
     text-align: center;
}

.post-wrapper {
     position: relative;
     margin-inline: 10%;     
}
</style>