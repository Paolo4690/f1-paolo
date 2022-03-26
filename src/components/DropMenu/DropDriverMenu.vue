<template>
    <div class="container">
      <ul class="list-inline">
        <li v-for="driver in arrDriver" :key="driver.driverId" class="list-inline-items">
          {{ `${driver.givenName} ${driver.familyName}` }}
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'DropDriverMenu',
  props: {
    arrDriver: Array,
  }
}
</script>

<style scoped lang="scss">

</style>
