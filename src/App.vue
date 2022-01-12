<template>
  <the-header title="Remainder"></the-header>
  <stored-resources :resources="storedResources"></stored-resources>
</template>

<script>
// import LearningResource from './components/learning-resources/LearningResource.vue';
import StoredResources from './components/learning-resources/StoredResources.vue';
import TheHeader from './components/Layouts/TheHeader.vue';
export default {
  components: {
    // LearningResource,
    TheHeader,
    StoredResources,
  },
  data() {
    return {
      storedResources: [
        {
          id: 'random-id-22141',
          title: 'Official vuejs tutor',
          description: 'this is course vuejs',
          link: 'http://www.github.com/rizalkhisyam',
        },
      ],
    };
  },
};
</script>
