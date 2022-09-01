<template>
  <!-- <Counter title="Counter"></Counter>
  <Counter></Counter>
  <Directives></Directives>
  <HelloWorld></HelloWorld>
  <indecison></indecison>
  <YesNoApi></YesNoApi> -->

</template>

<script>

  import HelloWorld from './components/HelloWorld.vue';
  import Counter from './components/Counter.vue';
  import Directives from './components/directives.vue';
  import Indecison from './components/Indecision.vue';
  import YesNoApi from './components/YesNoApi.vue';
  import register from './components/register.vue';
  import Create from './components/create.vue';
  import pageTitle from './components/pageTitle.vue';
  import header from './components/header.vue';

export default{
    name: 'App',
    components: {
  HelloWorld,
  Counter,
  Directives,
  Indecison,
  YesNoApi,
  register,
  Create,
  pageTitle,
  header
  }
}
</script>

<style scoped></style>