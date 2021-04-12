<template>
  <div id="hello">
    <datepicker
      v-model="date"
      :format="DatePickerFormat"
      :disabledDates="disabledDates"
       :displayFormat="'DD.MM.YYYY'"
       :first-day-of-week="1"
       calendar-class="my_calendar"
       input-class="textfield"
       :language="ptBR"
    >
    </datepicker>
  </div>
</template>

<script>
import Datepicker from "vuejs-datepicker";
import {ptBR} from 'vuejs-datepicker/dist/locale'

export default {
  components: {
    Datepicker,
  },

  data() {
    return {
      ptBR:ptBR,
       date: "",
       data: "",
      
      DatePickerFormat: "dd/MM/yyyy",
      disabledDates: {
        // to: new Date(Date.now() - 8640000),
        daysOfMonth: []
      },
       
      
    };
  },
  methods:{
    setDays(){
      this.disabledDates.daysOfMonth = [1,2,3,4,5,6,7,8,9,10,11,12]
      // var date = new Date()
      // this.model.date = date.toLocaleDateString()
    }
  },
  mounted(){
    this.setDays()
       var date = new Date()
      this.date1 = date.toLocaleDateString()
  }
};
</script>

<style >
.textfield{
 top: 100px;
margin-left: 600px;
width: 365px;
height: 38px;
background: #FFFFFF 0% 0% no-repeat padding-box;
border: 1px solid #CED4DA;
border-radius: 4px !important;
opacity: 1;
font-size: 20px;
color:#707a85 ;
outline: none;
text-align: left;
font: normal normal normal 20px/32px Poppins;
letter-spacing: 0px;
color: #9A9A9A;
}
.my_calendar{
top: 40px;
margin-left: 600px;
width: 365px !important;
height: 38px;
background: #FFFFFF 0% 0% no-repeat padding-box;
border: 1px solid #CED4DA  !important;
border-radius: 1px !important;
font: normal normal normal 20px/32px Poppins;
letter-spacing: 0px;
}
.vdp-datepicker__calendar .cell.day-header {
    font-size: 75%;
    white-space: nowrap;
    cursor: inherit;
    color: #2CD889;
}
.vdp-datepicker__calendar header span {
    display: inline-block;
    text-align: center;
    width: 71.42857142857143%;
    float: left;
    color: #2CD889;
}
.vdp-datepicker__calendar {
    position: absolute;
    z-index: 100;;
    width: 300px;
    height: 300px;
    border: 1px solid #ccc;
}
.vdp-datepicker * {
    box-sizing: border-box;
    font-weight: bold;
}
</style>
