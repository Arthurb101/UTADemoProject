<template>
<b-navbar toggleable="md" type="dark" variant="primary">

  <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

  <b-navbar-brand href="/">
    <b-img src ='http://www.rideuta.com/assets/img/uta-logo.svg'
    height="50"

    />
  </b-navbar-brand>

  <b-collapse is-nav id="nav_collapse">

    <b-navbar-nav style="text-color:white" >
      <b-nav-item href="#">Riderlol Info</b-nav-item>
      <b-nav-item href="#">Services</b-nav-item>
      <b-nav-item href="#">Doing Business</b-nav-item>


    </b-navbar-nav>

    <!-- Right aligned nav items -->
    <b-navbar-nav class="ml-auto">
      <b-nav-item-dropdown text="Riders Tools" :right="true" style="margin-right:60px;">
        <b-dropdown-item href="/RidersTools?q=TripComponent">Trip Planner</b-dropdown-item>
        <b-dropdown-item href="/RidersTools?q=ScheduleComponent">Schedules and Maps</b-dropdown-item>
        <b-dropdown-item href="/RidersTools?q=VehicleLocater">Vehicle locater</b-dropdown-item>
        <b-dropdown-item href="/RidersTools?q=RideTime">Ride Time</b-dropdown-item>
      </b-nav-item-dropdown>
      <b-button variant="primary" href="#">Buy Tickets!</b-button>
    </b-navbar-nav>

  </b-collapse>
</b-navbar>
</template>
<script>


export default {
  name: 'NavBarComponent',
  components: {
  }
}
</script>
