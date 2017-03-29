<template>
  <div class="container" id="app">
    <div class="row">
      <div class="col-sm-8 col-sm-offset-2">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h2 class="panel-title">Too Doo List ({{ todoCount }})</h2>
          </div>
          <ul class="list-group">
            <li class="list-group-item" v-for="item in todoList">
              <label class="form-check-label">
                <input class="form-check-input" type="checkbox" value="" v-model="item.checked">
                {{ item.name }}
              </label>
            </li>
          </ul>
          <div class="panel-heading">
            <h3 class="panel-title">Done List ({{ doneCount }})</h3>
          </div>
          <ul class="list-group">
            <li class="list-group-item" v-for="item in doneList">
              <label class="form-check-label">
                <input class="form-check-input" type="checkbox" value="" v-model="item.checked">
                {{ item.name }}
              </label>
            </li>
          </ul>
          <div class="panel-footer">
            <input type="text" class="form-control" placeholder="Type in new item..." v-model="message">  
            <a href="#" class="btn btn-large btn-block btn-primary" @click="add">Add item!</a>
          </div>
        </div>   
      </div>
    </div>
  </div>
</template>

<script>
module.exports = {
  data: function () {
    return {
      message: "Hello Vue!",
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
    add () {
      this.list.push({name: this.message, checked: false})
      this.message = ""
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
.done {
  text-decoration: line-through;
  font-weight: 400;
}
p {
  font-size: 2em;
  text-align: center;
}
</style>
