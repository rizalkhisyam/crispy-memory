<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="setResButtonMode"
      >Stored Resources</base-button
    >
    <base-button
      @click="setSelectedTab('add-resources')"
      :mode="setAddButtonMode"
      >Add Resources</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResources from './AddResources.vue';
export default {
  components: {
    StoredResources,
    AddResources,
  },
  data() {
    return {
      selectedTab: 'stored-resources',
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
  computed: {
    setResButtonMode() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },

    setAddButtonMode() {
      return this.selectedTab === 'add-resources' ? null : 'flat';
    },
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResources,
      deleteResource: this.removeItem,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },

    addResources(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        url: url,
      };

      this.storedResources.unshift(newResource);
      this.selectedTab = 'stored-resources';
    },

    removeItem(id) {
      const removeData = this.storedResources.filter((res) => {
        res.id !== id;
      });

      this.storedResources.splice(removeData, 1);
      console.log(id);
      console.log(this.storedResources);
    },
  },
};
</script>
