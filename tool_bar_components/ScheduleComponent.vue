<template>
<div>
<h1>Schedule</h1>


<div>
  <b-form-group horizontal
                :label-cols="2"
                label-size="lg"
                label="Date"
                style="text-align:left"
              label-for="the_date">
              <no-ssr>
                 <date-picker  style="width:50%; float:left" lang="en" :v-model="state"/>
               </no-ssr>
  </b-form-group>
  <b-form-group horizontal
                :label-cols="2"
                label-size="lg"
                label="Starting Stop"
                style="text-align:left"
                label-for="input_default">
  <b-form-select id="exampleInput3"
    :options="stops"
    v-model="column_pick1"
    size="lg"
    >
    Select
  </b-form-select>
  </b-form-group>
  <b-form-group horizontal
                :label-cols="2"
                label-size="lg"
                label="Destination Stop"
                style="text-align:left"
                label-for="input_lg">
                <b-form-select id="exampleInput3"
                  :options="stops"
                  v-model="column_pick2"
                  size="lg"
                  >
                  Select
                </b-form-select>
    <b-button :pressed="north_bound" v-on:click="change_direct_north()"  size="lg" variant="outline-success" style="float:left;margin-top:15px; margin-right:20px"> northbound </b-button>
    <b-button :pressed="!north_bound" v-on:click="change_direct_south()" size="lg" variant="outline-danger" style="float:left;margin-top:15px; margin-right:20px" > southbound </b-button>
  </b-form-group>
  <b-form-group>
    <b-button v-on:click="choose_coloumns()" size="lg" variant="primary" style="margin-right:20px"> view selected stops </b-button>
    <b-button v-on:click="show_all_coloumns()" size="lg" variant="primary"> view all stops </b-button>
  </b-form-group>


</div>
  <b-table striped hover :items="items" :fields="fields"></b-table>


</div>

</template>

<script>




export default {
  name: 'ScheduleComponent',
  components: {

  },
   methods: {
    choose_coloumns: function () {
      this.fields = []
      for (var i = 0; i < this.old_fields.length; i++) {
        if(this.old_fields[i].label == this.column_pick1 || this.old_fields[i].label == this.column_pick2 )
        {
          this.fields.push(this.old_fields[i])
        }


    }

    },

    show_all_coloumns: function(){
      this.fields = this.old_fields
    },
    change_direct_south: function () {

      if(this.north_bound)
      {

        this.fields.reverse();
        this.north_bound = false;
      }
        //items.reverse()
    },
    change_direct_north: function () {

      if(!this.north_bound)
      {
        this.fields.reverse();
        this.north_bound = true;
      }
        //items.reverse()
    },
  },
  data () {
    var d = new Date();
    return {
      // Note 'isActive' is left out and will not appear in the rendered table
      north_bound:true,
      column_pick1: "",
      column_pick2: "",
      state: {
        date: new Date(d.getFullYear(), d.getMonth(),  d.getDate())
      },
      stops:[
        { text: 'Select One', value: null },
        'Provo Central Station','Orem Central Station','American Fork Station',
        'Lehi Station','Draper Station','South Jordan Station','Murray Central Station',
        'Salt Lake Central Station','North Temple Station','Woods Cross Station','Farmington Station',
        'Clearfield Station','Roy Station','Ogden Station'
      ],
      old_fields:
      [
        {
          key: 'provo_central_station',
          label: 'Provo Central Station',
        },
        {
          key: 'orem_central_station',
          label: 'Orem Central Station',
        },
        {
          key: 'american_fork_station',
          label: 'American Fork Station',
        },
        {
          key: 'lehi_station',
          label: 'Lehi Station',
        },
        {
          key: 'draper_station',
          label: 'Draper Station',
        },
        {
          key: 'south_jordan_station',
          label: 'South Jordan Station',
        },
        {
          key: 'murray_central_station',
          label: 'Murray Central Station',
        },
        {
          key: 'salt_lake_central_station',
          label: 'Salt Lake Central Station',
        },
        {
          key: 'north_temple_station',
          label: 'North Temple Station',
        },
        {
          key: 'woods_cross_station',
          label: 'Woods Cross Station',
        },
        {
          key: 'farmington_station',
          label: 'Farmington Station',
        },
        {
          key: 'clearfield_station',
          label: 'Clearfield Station',
        },
        {
          key: 'roy_station',
          label: 'Roy Station',
        },
        {
          key: 'ogden_station',
          label: 'Ogden Station',
        }

      ],

      fields: [
        {
          key: 'provo_central_station',
          label: 'Provo Central Station',
        },
        {
          key: 'orem_central_station',
          label: 'Orem Central Station',
        },
        {
          key: 'american_fork_station',
          label: 'American Fork Station',
        },
        {
          key: 'lehi_station',
          label: 'Lehi Station',
        },
        {
          key: 'draper_station',
          label: 'Draper Station',
        },
        {
          key: 'south_jordan_station',
          label: 'South Jordan Station',
        },
        {
          key: 'murray_central_station',
          label: 'Murray Central Station',
        },
        {
          key: 'salt_lake_central_station',
          label: 'Salt Lake Central Station',
        },
        {
          key: 'north_temple_station',
          label: 'North Temple Station',
        },
        {
          key: 'woods_cross_station',
          label: 'Woods Cross Station',
        },
        {
          key: 'farmington_station',
          label: 'Farmington Station',
        },
        {
          key: 'clearfield_station',
          label: 'Clearfield Station',
        },
        {
          key: 'roy_station',
          label: 'Roy Station',
        },
        {
          key: 'ogden_station',
          label: 'Ogden Station',
        }

      ],
      items: [
        { provo_central_station:"NO STOP",orem_central_station:"NO STOP",american_fork_station:"NO STOP",lehi_station:"NO STOP",draper_station:"NO STOP",south_jordan_station:"NO STOP",murray_central_station:"NO STOP",salt_lake_central_station:"4:50AM",north_temple_station:"4:52AM",woods_cross_station:"5:00AM" ,farmington_station: '5:08AM', clearfield_station: '5:08AM', roy_station: '5:16AM', ogden_station: "5:24AM" },
        { provo_central_station:"4:54AM",orem_central_station:"5:02AM",american_fork_station:"5:10AM",lehi_station:"5:18AM",draper_station:"5:26AM",south_jordan_station:"5:34AM",murray_central_station:"5:42AM",salt_lake_central_station:"5:50AM",north_temple_station:"5:52AM",woods_cross_station:"6:00AM" ,farmington_station: '6:08AM', clearfield_station: '6:08AM', roy_station: '6:16AM', ogden_station: "6:24AM" },
        { provo_central_station:"5:54AM",orem_central_station:"6:02AM",american_fork_station:"6:10AM",lehi_station:"6:18AM",draper_station:"6:26AM",south_jordan_station:"6:34AM",murray_central_station:"6:42AM",salt_lake_central_station:"6:50AM",north_temple_station:"6:52AM",woods_cross_station:"7:00AM" ,farmington_station: '7:08AM', clearfield_station: '7:08AM', roy_station: '7:16AM', ogden_station: "7:24AM" },
        { provo_central_station:"6:54AM",orem_central_station:"7:02AM",american_fork_station:"7:10AM",lehi_station:"7:18AM",draper_station:"7:26AM",south_jordan_station:"7:34AM",murray_central_station:"7:42AM",salt_lake_central_station:"7:50AM",north_temple_station:"7:52AM",woods_cross_station:"8:00AM" ,farmington_station: '8:08AM', clearfield_station: '8:08AM', roy_station: '8:16AM', ogden_station: "8:24AM" },
        { provo_central_station:"7:54AM",orem_central_station:"8:02AM",american_fork_station:"8:10AM",lehi_station:"8:18AM",draper_station:"8:26AM",south_jordan_station:"8:34AM",murray_central_station:"8:42AM",salt_lake_central_station:"8:50AM",north_temple_station:"8:52AM",woods_cross_station:"9:00AM" ,farmington_station: '9:08AM', clearfield_station: '9:08AM', roy_station: '9:16AM', ogden_station: "9:24AM" },
        { provo_central_station:"8:54AM",orem_central_station:"9:02AM",american_fork_station:"9:10AM",lehi_station:"9:18AM",draper_station:"9:26AM",south_jordan_station:"9:34AM",murray_central_station:"9:42AM",salt_lake_central_station:"9:50AM",north_temple_station:"9:52AM",woods_cross_station:"10:00AM" ,farmington_station: '10:08AM', clearfield_station: '10:08AM', roy_station: '10:16AM', ogden_station: "10:24AM" },
        { provo_central_station:"9:54AM",orem_central_station:"10:02AM",american_fork_station:"10:10AM",lehi_station:"10:18AM",draper_station:"10:26AM",south_jordan_station:"10:34AM",murray_central_station:"10:42AM",salt_lake_central_station:"10:50AM",north_temple_station:"10:52AM",woods_cross_station:"11:00AM" ,farmington_station: '11:08AM', clearfield_station: '11:08AM', roy_station: '11:16AM', ogden_station: "11:24AM" },
        { provo_central_station:"10:54AM",orem_central_station:"11:02AM",american_fork_station:"11:10AM",lehi_station:"11:18AM",draper_station:"11:26AM",south_jordan_station:"11:34AM",murray_central_station:"11:42AM",salt_lake_central_station:"11:50AM",north_temple_station:"11:52AM",woods_cross_station:"12:00PM" ,farmington_station: '12:08PM', clearfield_station: '12:08PM', roy_station: '12:16PM', ogden_station: "12:24PM" },
        { provo_central_station:"11:54AM",orem_central_station:"12:02PM",american_fork_station:"12:10PM",lehi_station:"12:18PM",draper_station:"12:26PM",south_jordan_station:"12:34PM",murray_central_station:"12:42PM",salt_lake_central_station:"12:50PM",north_temple_station:"12:52PM",woods_cross_station:"1:00PM" ,farmington_station: '1:08PM', clearfield_station: '1:08PM', roy_station: '1:16PM', ogden_station: "1:24PM" },
        { provo_central_station:"12:54PM",orem_central_station:"1:02PM",american_fork_station:"1:10PM",lehi_station:"1:18PM",draper_station:"1:26pM",south_jordan_station:"1:34PM",murray_central_station:"1:42PM",salt_lake_central_station:"1:50PM",north_temple_station:"1:52PM",woods_cross_station:"2:00AM" ,farmington_station: '2:08AM', clearfield_station: '2:08PM', roy_station: '2:16PM', ogden_station: "2:24PM" },
        { provo_central_station:"1:54PM",orem_central_station:"2:02PM",american_fork_station:"2:10PM",lehi_station:"2:18PM",draper_station:"2:26pM",south_jordan_station:"2:34PM",murray_central_station:"2:42PM",salt_lake_central_station:"2:50PM",north_temple_station:"2:52pM",woods_cross_station:"3:00AM" ,farmington_station: '3:08AM', clearfield_station: '3:08PM', roy_station: '3:16PM', ogden_station: "3:24PM" },
        { provo_central_station:"2:54PM",orem_central_station:"3:02PM",american_fork_station:"3:10PM",lehi_station:"3:18PM",draper_station:"3:26PM",south_jordan_station:"3:34PM",murray_central_station:"3:42PM",salt_lake_central_station:"3:50pM",north_temple_station:"3:52PM",woods_cross_station:"4:00AM" ,farmington_station: '4:08AM', clearfield_station: '4:08PM', roy_station: '4:16PM', ogden_station: "4:24PM" },
        { provo_central_station:"3:54PM",orem_central_station:"4:02PM",american_fork_station:"4:10PM",lehi_station:"4:18PM",draper_station:"4:26PM",south_jordan_station:"4:34PM",murray_central_station:"4:42PM",salt_lake_central_station:"4:50PM",north_temple_station:"4:52PM",woods_cross_station:"5:00AM" ,farmington_station: '5:08AM', clearfield_station: '5:08PM', roy_station: '5:16PM', ogden_station: "5:24PM" },
        { provo_central_station:"4:54PM",orem_central_station:"5:02PM",american_fork_station:"5:10PM",lehi_station:"5:18PM",draper_station:"5:26PM",south_jordan_station:"5:34PM",murray_central_station:"5:42PM",salt_lake_central_station:"5:50pM",north_temple_station:"5:52PM",woods_cross_station:"6:00AM" ,farmington_station: '6:08AM', clearfield_station: '6:08PM', roy_station: '6:16PM', ogden_station: "6:24PM" },
      ]
    }
  }
}
</script>
<style>

</style>
