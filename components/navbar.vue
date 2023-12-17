
import type { buildAssetsDir } from 'nuxt/dist/core/runtime/nitro/paths';
<template>
     <header>
     <nav>
          <ul>
               <!-- continue here -->
          <nuxt-link to="/">
         
               <li class="homepage">Homepage</li>
          </nuxt-link>

          </ul>
     </nav>
</header>
</template>

<style>
header {
  background-color: cadetblue;
  padding: 1rem;
  color: white;
}

.homepage {
  font-size: 2rem;
  color: white;
  font-weight: 700;
}
a {
  text-decoration: none;
}

</style>


