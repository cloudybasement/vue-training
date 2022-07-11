<template>
  <div>
    <TheHeader/>
    <button @click="setActiveComponent('active-goals')">Active Goals</button>
    <button @click="setActiveComponent('manage-goals')">Manage Goals</button>
    <!-- <ActiveGoals v-if="selectedComponent == 'active-goals'"/>
    <ManageGoals v-if="selectedComponent == 'manage-goals'"/> -->
    <keep-alive>
      <component :is="activeComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue';
export default {
    data() {
        return {
          activeComponent: 'active-goals',
            activeUser: {
                name: "Maximilian Schwarzmüller",
                description: "Site owner and admin",
                role: "admin",
            },
        };
    },
    methods: {
      setActiveComponent(component) {
        this.activeComponent = component;
      }
    },
    components: { TheHeader, ActiveGoals, ManageGoals }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>