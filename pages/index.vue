<template>
  <div title="boundary">
    <NavBarComponent/>

      <b-container style="text-align: center;">
        <b-jumbotron >
          <div>

            <h1 class="title">
              UTA Demo Website
            </h1>
            <h2 class="subtitle">
              taking the look and feel of UTA web experience from Meh! to WOW!
            </h2>

          </div>
          </b-jumbotron>
          <h3>compare and contrast the feature I built!</h3>
          <b-button href="https://www.rideuta.com/Rider-Tools/Schedules-and-Maps" style="margin-right: 40px; margin-bottom:20px;" id="exButton1" size="lg" variant="danger">Official UTA Website</b-button>
          <b-button style="margin-bottom:20px" href="/RidersTools?q=ScheduleComponent" id="exButton2" size="lg" variant="primary">UTA Demo Website</b-button>
          <div style="height: 100px;">
            <img style="width:100%; height:550px " src="https://i.ytimg.com/vi/aZfszZqR7i4/maxresdefault.jpg"></img>
          </div>
        </b-container>



      <b-tooltip target="exButton1" placement="bottom" > MEH!</b-tooltip>

      <!-- HTML title specified via default slot -->
      <b-tooltip target="exButton2" placement="bottom">
        WOW!
      </b-tooltip>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import NavBarComponent from '~/components/NavBarComponent'

export default {
  components: {
    Logo,
    NavBarComponent
  }
}
</script>

<style>

.title
{
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
.subtitle
{
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
.links
{
  padding-top: 15px;
}
</style>
