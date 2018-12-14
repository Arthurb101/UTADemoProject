<template>

<div>
  <h1>Schedule</h1>
  <b-button-group>
    <b-button variant="outline-primary" :pressed="Rail" v-on:click="Rail = true">Rail</b-button>
    <b-button variant="outline-primary" :pressed="!Rail" v-on:click="Rail = false">Bus</b-button>
  </b-button-group>
<div v-if="Rail">
  <button style="border-color: #007bff;background-color: #007bff;
  " class="scheduleToolBarButtons"> 2 Trax Blue Line </button>
  <button
  style="border-color: red;background-color: red;
  "
   class="scheduleToolBarButtons"> 703 Trax Red Line </button>
  <button
  style="border-color: green;background-color: green;
  "
   class="scheduleToolBarButtons"> 704 Trax Green Line </button>
  <button
  style="border-color: #808080;background-color: #808080;
  "
   class="scheduleToolBarButtons"> S-Line </button>
  <button
  style="border-color: #9622B2;background-color: #9622B2;
  "
   class="scheduleToolBarButtons"> Frontrunner </button>
</div>

<div v-else>
  <button style="border-color: green;background-color: green;
  " class="scheduleToolBarButtons"> 2 </button>
  <button style="border-color: red;background-color: red;
  " class="scheduleToolBarButtons"> 2X</button>
  <button style="border-color: #007bff;background-color: #007bff;
  " class="scheduleToolBarButtons"> 3 </button>
  <button style="border-color: #007bff;background-color: #007bff;
  " class="scheduleToolBarButtons"> 6 </button>
  <button style="border-color: #007bff;background-color: #007bff;
  " class="scheduleToolBarButtons"> 9 </button>
</div>

</div>

</template>
<script>


export default {
  name: 'ScheduleToolBar',
  components: {

  },

data: function () {
  return {
    Rail: true
  }
},
}
</script>
<style>

.scheduleToolBarButtons
{
  width:90%;
  cursor: pointer;
  color:white;
  border: 1px solid transparent;
  border-radius: 0.3rem;
  display: block;
  font-weight: 400;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  margin-top: 20px;
}
  .marginButton
  {
    display: block;
    margin-top: 20px;
  }

</style>
