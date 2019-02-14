<template>
<div>
<table class="table topbottom">
  <tbody>
    <tr>
      <td class="noBorder"> <span class="topbottom">{{top}}</span></td>
</tr>
<tr>
       <td class="noBorder"> <span id="response" class="topbottom">{{bottom}}</span></td>
</tr>
  </tbody>
</table>
  </div>

</template>
<script>
export default {
  name: 'TopBottom',
  props: ['top', 'bottom']

}
</script>
<style>
.topbottom{
    display: block;
    white-space: nowrap;
  overflow: hidden;
}

.table td, .table th {
    border: 0px;
}
</style>
