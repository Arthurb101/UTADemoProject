<template>

<div>
  <h1>Rider Tozzz</h1>
  <div style="display:block;" >
    <b-button :active="true" variant="outline-primary" class="toolBarButtons" href="/RideTime">Trip Planner</b-button>
    <b-button variant="outline-primary" class="toolBarButtons" href="/Schedules">Schedule and Map</b-button>
    <b-button variant="outline-primary" class="toolBarButtons" href="/Trip">Vehicle Locater</b-button>
    <b-button variant="outline-primary" class="toolBarButtons" href="/VehicleLocater">Ride Time</b-button>
  </div>
</div>

</template>
<script>


export default {
  name: 'ToolBar',
  components: {

  }
}
</script>
<style>
  .toolBarButtons
  {

    display: block;
    margin-top: 20px;
  }
</style>
