<template>
  <div class="container">
    <div>Date: {{ date.toString() }}</div>
    <div>Day: {{ getDay() }} <br /></div>
    <div>Month: {{ getMonth() }}</div>

    <div>
      <div class="input-1">
        <label for="day"> Add Day </label>
        <input type="number" id="day" v-model="day" />
      </div>

      <div class="input-2">
        <label for="month"> Add Month </label>
        <input type="number" id="month" v-model="month" />
      </div>

      <p>
        {{ day && addDay(day).toString() }}
        <br />
        {{ month && addMonth(month).toString() }}
      </p>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import useDate from "./components/useDate";

export default {
  setup() {
    const { date, getDay, getMonth, addDay, addMonth } = useDate();
    const day = ref(null);
    const month = ref(null);

    return { date, getDay, getMonth, addDay, addMonth, day, month };
  },
};
</script>

<style>

body {
  background-color: #f1f1f1;
}
.container {
  display: flex;
  flex-direction: column;
  background-color: rgb(0, 34, 126);
  max-width: 80%;
  margin: 0% auto;
  margin-top: 40px;
  gap: 6px;
  color: #f1f1f1 ;
  border-radius: 10px;
  padding-left: 20px;
  padding-top: 20px;
  padding-right: 20px;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  box-shadow: rgb(157, 182, 250) 0px 4px 12px;
  /* text-align: center; */
  /* justify-content: center; */
  /* align-items: center; */
}

input {
  border-radius: 4px;
  border: 1px solid #f1f1f1;
}

.input-1 {
  margin-top: 20px;
}

.input-2 {
  margin-top: 10px;
}
</style>
