<template>
    <div class="container">
      <ul class="list-inline">
        <li v-for="team in arrTeam" :key="team.constructorId" class="list-inline-items">
          {{ team.name }}
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'DropTeamMenu',
  props: {
    arrTeam: Array,
  }
}
</script>

<style scoped lang="scss">

</style>
