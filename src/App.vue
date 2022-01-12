<template>
  <the-header title="Remainder"></the-header>
  <the-resources></the-resources>
  <!-- <stored-resources :resources="storedResources"></stored-resources> -->
</template>

<script>
// import LearningResource from './components/learning-resources/LearningResource.vue';
// import StoredResources from './components/learning-resources/StoredResources.vue';
import TheHeader from './components/Layouts/TheHeader.vue';
import TheResources from './components/learning-resources/TheResources.vue';
export default {
  components: {
    // LearningResource,
    TheHeader,
    TheResources,
  },
  data() {
    return {};
  },
};
</script>
