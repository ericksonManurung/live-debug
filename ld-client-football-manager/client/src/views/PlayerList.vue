<template>
  <table class="table container mb-5">
    <thead class="thead-dark">
      <tr>
        <th scope="col">No</th>
        <th scope="col">Name</th>
        <th scope="col">Position</th>
        <th scope="col">Height</th>
        <th scope="col">Scores</th>
        <th scope="col">Actions</th>
      </tr>
    </thead>
    <tbody>
      <PlayerListItem
        v-for="(player,num) in players"
        :key="player.id"
        :player="player"
        :num="num"
      />
    </tbody>
  </table>
</template>

<script>
import PlayerListItem from '../components/PlayerListItem'

export default {
  name: 'PlayerList',
  components: {
    PlayerListItem
  },
  computed: {
    players () {
      return this.$store.state.players
    }
  },
  created () {
    this.$store.dispatch('fetchPlayers')
    this.$store.dispatch('fetchTeams')
  }
}
</script>

<style>

</style>
