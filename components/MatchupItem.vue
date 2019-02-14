<template>

<div class="box field is-horizontal">
  <div class="field-label">
    {{matchup.Game.properties.DateTime}}
  </div>
  <div class="field-body">
    <div class="field">
      <TopBottom 
        :top="matchup.Game.properties.AwayTeam"
        :bottom="matchup.Game.properties.HomeTeam"
      />
    </div>
    <div class="field">
      <TopBottom 
        :top="matchup.Game.properties.PointSpread"
        :bottom="matchup.Game.properties.PointSpread"
      />
    </div>
    <div class="field">
      <TopBottom top="-300" bottom="+225"></TopBottom>
    </div>
    <div class="field">
      <TopBottom top="O57" bottom="U57"></TopBottom>
    </div>
  </div>
</div>

</template>

<script>

import TopBottom from '~/components/topbottom.vue'

export default {
  name: 'MatchupItem',
  props: ['matchup', 'id'],

  data: function() {
    return {
    }
  },

  components: {
    TopBottom    
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

