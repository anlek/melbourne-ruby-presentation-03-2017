<template>
  <div class="container" id="app">
    <div class="row">
      <div class="col-sm-8 col-sm-offset-2">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h2 class="panel-title">Too Doo List ({{ todoCount }})</h2>
          </div>
          <ul class="list-group">
            <item v-for="item in todoList" :key="item.id" :item="item" @delete="removeItem" />
          </ul>
          <div class="panel-heading">
            <h3 class="panel-title">Done List ({{ doneCount }})</h3>
          </div>
          <ul class="list-group">
            <item v-for="item in doneList" :key="item.id" :item="item" @delete="removeItem" />
          </ul>
          <div class="panel-footer">
            <input type="text" class="form-control" placeholder="Type in new item..." v-model="newItem" @keyup.enter="addItem">  
            <a href="#" class="btn btn-large btn-block btn-primary" @click="addItem">Add item!</a>
          </div>
        </div>   
      </div>
    </div>
  </div>
</template>

<script>
import item from './todoItem'
export default {
  components: { 
    item 
  },
  data: function () {
    return {
      newItem: '',
      list: [
        { name: "Build",    checked: false },
        { name: "A",        checked: false },
        { name: "Todo",     checked: false },
        { name: "List",     checked: false },
        { name: "Allow",    checked: true  },
        { name: "Complete", checked: true  },
        { name: "All",      checked: true  }
      ]
    }
  },
  computed: {
    todoList () {
      return this.list.filter(item => {
        return !item.checked
      })
    },
    todoCount () {
      return this.todoList.length
    },
    doneList () {
      return this.list.filter(item => {
        return item.checked
      })
    },
    doneCount() {
      return this.doneList.length
    }
  },
  methods: {
    addItem () {
      this.list.push({name: this.newItem, checked: false})
      this.newItem = ""
    },
    removeItem(item) {
      let idx = this.list.indexOf(item)
      if (idx > -1) {
        this.list.splice(idx, 1)
      }
    }
  }
}
</script>

<style scoped>
.container {
  margin-top: 25px;
}
.panel-heading{
  text-align: center;
}
</style>
