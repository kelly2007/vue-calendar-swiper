<template>
  <div id="app">
      <div>
        <button @click="lookThisMonth">查看当月</button>
      </div>
      <div>
        <vue-calendar-swiper
          ref="calendar1"
          :events="calendar1.events"
          :lunar="calendar1.lunar"
          :value="calendar1.value"
          :values="calendar1.values"
          :weeks="calendar1.weeks"
          :months="calendar1.months"
          :totalMonth="calendar1.totalMonth"
          @select="calendar1.select"
          @selectMonth="calendar1.selectMonth"
          @selectYear="calendar1.selectYear"
        ></vue-calendar-swiper>
      </div>
    </div>
</template>

<script>
//  import calendar from './components/calendar.vue'
  export default {
    name: 'app',
//    components: {
//      calendar
//    },
    data () {
      return {
        year: 0,
        month: 0,
        day: 0,
        calendar1:{
          totalMonth:14,   //一共显示几个月
//          value:[2017,11,1], //默认日期  如果没设置就默认选中今天
          values:[[2018,5,1],[2018,6,2],[2018,6,6],[2018,7,11],[2018,8,11],[2018,8,12],[2018,8,14]], //有哪些时间点是被选中的
//          lunar:true, //显示农历
//          weeks:['Sun', 'Mon' , 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'],
//          months:['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
//          events:{
//            '2017-7-7':'$408',
//            '2017-7-20':'$408',
//            '2017-7-21':'$460',
//            '2017-7-22':'$500',
//          },
          select(value){
            console.log(value.toString());
          },
          selectMonth(month,year){
            console.log(year,month)
          },
          selectYear(year){
            console.log(year)
          },
          timestamp:Date.now()
        }
      }
    },
    methods: {
      lookThisMonth(){
        this.$refs.calendar1.setToday()
      }
    },
    created(){

    }
  }
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
