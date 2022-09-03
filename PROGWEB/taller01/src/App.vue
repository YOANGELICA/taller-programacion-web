<template>
  <TimeFormat></TimeFormat>
  <PhoneCall></PhoneCall>
  <Greetings></Greetings>
  <ThreeNumbers></ThreeNumbers>
  <MinToMax></MinToMax>
  <OddNumber></OddNumber>
  <salary></salary>
  <Divide></Divide>
  <Nine></Nine>
  <Grades></Grades>
  <Grades2></Grades2>
</template>

<script>
  import TimeFormat from './components/TimeFormat.vue';
  import PhoneCall from './components/PhoneCall.vue';
  import Greetings from './components/Greetings.vue';
  import ThreeNumbers from './components/ThreeNumbers.vue';
  import MinToMax from './components/MinToMax.vue';
  import OddNumber from './components/OddNumber.vue';
  import Salary from './components/Salary.vue';
  import Divide from './components/Divide.vue';
  import Nine from './components/Nine.vue';
  import Grades from './components/Grades.vue';
  import Grades2 from './components/Grades2.vue';

  export default{
      name: 'App',
      components: {
    TimeFormat,
    PhoneCall,
    Greetings,
    Salary,
    MinToMax,
    OddNumber,
    ThreeNumbers,
    Divide,
    Nine,
    Grades,
    Grades2
    }
  }
</script>

<style scoped></style>
