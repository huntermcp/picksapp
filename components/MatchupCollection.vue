<template>

<div id="matchup-list">
    <div><p>Matchups</p></div>
  <ul>
    <MatchupItem
				v-for="matchup in matchups"
				:key="matchup.id"
				:matchup="matchup"
				
			/>
  </ul>
</div>
</template>

<script>
const axios = require('axios')

import MatchupItem from  '~/components/MatchupItem.vue'
const gameMock = require('~/assets/test/mocks/sports.js').gameMock

export default {
    name: 'MatchupCollection',

    data () {
      return {
          body: null,
          matchups: []
      }           
    },

    mounted () {
      axios
        .get('http://localhost:4000/matchups')
        .then(response => {
            this.matchups = response.data.body
            console.log(response.data.body)
            })
    }, 

    components: {
        MatchupItem
  }
}




</script>




<style>
.competitors{
    text-align:center;
}
.topbottom{
    display: block;
    white-space: nowrap;
  overflow: hidden;
}
</style>

