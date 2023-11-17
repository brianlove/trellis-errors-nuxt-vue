<script setup>

// Importing `Force` works and appears to give the expected result...
import * as Force from '@sayari/trellis/layout/force';

// ...but importing WebGL fails with an HTTP 500: "require() of ES Module ... not supported"
// import * as WebGL from '@sayari/trellis/renderers/webgl';


// This is the same Trellis component as used in the plain-Vue version (without Nuxt):
// import Trellis from '../components/Trellis.vue';


console.info("Force:", Force); // DEBUG
// console.info("WebGL:", WebGL); // DEBUG
</script>

<template>
  <div>
    <title>Trellis test app with Nuxt</title>
    <h2>Index page</h2>
    <p>
      Index page, because for some reason Nuxt doesn't ship with one by default?
    </p>
    <p>
      Uncomment the Trellis imports to see if it works with Nuxt.
    </p>

    <!-- <Trellis /> -->
  </div>
</template>

<style scoped>
.trellis-container {
  background-color: #eee;
  border: 1px solid #666;
  height: 400px;
  width: 600px;
}
</style>
