<script src="../../assets/js/vue.js"></script>

<template>

  <div className="app">
  <div class="container">
    <div class="row row-cols-6">
      <div class="col" v-for="(n,index) in 60 ">
        <button class="btn btn-success border ">{{hour+':' + (index < 10 ? '0' + index : index)}}</button>
      </div>
    </div>
  </div>
  </div>

</template>
<script>

/*<div className="app">
  <table className="table table-sm">
    <tr v-for="(n,index) in 60 ">
      <td></td>
      <td>
        <button>{{hour+':' + (index < 10 ? '0' + index : index)}}</button>
      </td>
    </tr>
  </table>
</div>*/


export default {
  name: 'App',
  data() {
    return {
      date: '',
      hour: '',
      minute: '',
    }
  },
  created() {
    this.getCurrentTime();

  },
  methods: {
    getCurrentTime() {
      let dateTime = new Date();
      this.hour = dateTime.getHours();
      this.minute= (this.minute>10) + dateTime.getMinutes();
      this.date = this.hour +':' +this.minute
      console.log(dateTime);
      console.log( (dateTime.getMinutes()<10?'0':'') + dateTime.getMinutes() );
    }
  }

}
</script>
