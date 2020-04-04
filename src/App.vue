<template>
  <div id="app">
    <AppTitle/>

    <AppContent ref="content"
                v-bind:items="items"
                v-on:clear-adding="clearAdding">
    </AppContent>

    <AddItem  ref="addItem"
              v-bind:items="items"
              v-on:clear-editing="clearEditingContent">
    </AddItem>

    <AppFooter/>
  </div>
</template>

<script>
  import AppTitle from './components/AppTitle'
  import AppFooter from './components/AppFooter'
  import AppContent from './components/AppContent'
  import AddItem from './components/AddItem'
  var items = [
    {
      value: "学习HTML",
      isDone: true,
      isEditing: false,
    },
    {
      value: "学习CSS",
      isDone: true,
      isEditing: false,
    },
    {
      value: "学习JavaScript",
      isDone: false,
      isEditing: false,
    },
    {
      value: "学习jQuery",
      isDone: false,
      isEditing: false,
    },
    {
      value: "学习Vue",
      isDone: true,
      isEditing: false,
    },];
  export default {
    name: 'App',
    components: {
      AppFooter,
      AppTitle,
      AppContent,
      AddItem
    },
    methods: {
      clearEditingContent: function () {
        this.$refs.content.clearEditing();     // 执行函数
      },
      clearAdding: function ($event) {
        this.$refs.addItem.isAdding = $event;   // 直接设定值
      }
    },
    data () {
      return {
        items: items,
      }
    }
  };
</script>

<style>
  #app {
    padding: 20px 20px 80px 20px;
    width: 750px;
    margin: 100px auto;
    background-color: #fff;
    /*color: #fff;*/
    border-radius: 3px;
    position: relative;
  }
</style>



