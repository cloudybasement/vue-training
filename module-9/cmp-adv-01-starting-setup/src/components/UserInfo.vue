<template>
  <BaseCard>
    <template #header>
      <h3>{{ fullName }}</h3>
      <BaseBadge :type="role" :caption="role.toUpperCase()" />
    </template>
    <template #default>
      <p>{{ infoText }}</p>
    </template>
  </BaseCard>
</template>

<script>
export default {
  props: ['fullName', 'infoText', 'role'],
};
</script>

<style scoped>
</style>