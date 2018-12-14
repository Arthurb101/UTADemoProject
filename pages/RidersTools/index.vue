<template>
<div >
      <NavBarComponent/>
      <b-row style="margin:0px;" class="text-center">
          <b-col >
                <h1>Rider Tools</h1>
                  <div style="display:block;" >
                    <b-button :pressed="TripBool" v-on:click="currentTabComponent = 'TripComponent' ; changeBool()" variant="outline-primary" class="toolBarButtons" >Trip Planner</b-button>
                    <b-button :pressed="ScheduleBool" v-on:click="currentTabComponent = 'ScheduleComponent'; changeBool()" variant="outline-primary" class="toolBarButtons" >Schedule and Maps</b-button>
                    <b-button  :pressed="VehicleBool" v-on:click="currentTabComponent = 'VehicleLocater'; changeBool()" variant="outline-primary" class="toolBarButtons" >Vehicle Locater</b-button>
                    <b-button :pressed="RideBool" v-on:click="currentTabComponent = 'RideTime'; changeBool()" variant="outline-primary" class="toolBarButtons" >Ride Time</b-button>
                  </div>
                  <ScheduleToolBar v-if="currentTabComponent == 'ScheduleComponent'" />
          </b-col>
          <b-col cols="10">
                <component v-bind:is="currentTabComponent"></component>
          </b-col>

      </b-row>
    

</div>

</template>
<script>

import NavBarComponent from '~/components/NavBarComponent';
import ToolBar from '~/components/ToolBar';
import TheFooter from '~/components/TheFooter';
import RideTime from '~/tool_bar_components/RideTime';
import ScheduleComponent from '~/tool_bar_components/ScheduleComponent';
import TripComponent from '~/tool_bar_components/TripComponent';
import VehicleLocater from '~/tool_bar_components/VehicleLocater';
import ScheduleToolBar from '~/components/ScheduleToolBar';

export default {
  name: 'RidersTools',
  components: {
        NavBarComponent,
        ToolBar,
        TheFooter,
        RideTime,
        ScheduleComponent,
        TripComponent,
        VehicleLocater,
        ScheduleToolBar
  },
methods: {
    changeBool()
    {
        this.TripBool = false;
        this.ScheduleBool = false;
        this.VehicleBool = false;
        this.RideBool = false;
      if(this.currentTabComponent == "TripComponent")
      {
          this.TripBool = true;
      }
      else if(this.currentTabComponent == "ScheduleComponent")
      {
        this.ScheduleBool = true;
      }
      else if(this.currentTabComponent == "VehicleLocater")
      {
        this.VehicleBool = true;
      }
      else if(this.currentTabComponent == "RideTime")
      {
        this.RideBool = true;
      }
    }
  },
  data: function () {
    return {
      currentTabComponent: this.$route.query.q,
      TripBool:false,
      ScheduleBool:true,
      RideBool:false,
      VehicleBool:false,
    }
  },

}
</script>
<style>
  .toolBarButtons
  {
    width:90%;
    display: block;
    margin-top: 20px;
  }
</style>
