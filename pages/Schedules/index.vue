<template>
  <div >
        <NavBarComponent/>
        <b-row style="margin:0px;" class="text-center">
            <b-col >
                   <ToolBar/>
                   <ScheduleToolBar/>
            </b-col>
            <b-col cols="10">2 of 2 (wider)</b-col>

        </b-row>
        <TheFooter/>

  </div>
</template>
<script>

import NavBarComponent from '~/components/NavBarComponent';
import ToolBar from '~/components/ToolBar';
import TheFooter from '~/components/TheFooter';
import ScheduleToolBar from '~/components/ScheduleToolBar';

export default {
  name: 'Schedules',
  components: {
           ToolBar,
          NavBarComponent,

         TheFooter,
         ScheduleToolBar

  }
}
</script>
