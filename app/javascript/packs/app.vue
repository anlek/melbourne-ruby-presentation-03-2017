<template>
  <div class="container" id="app">
    <div class="row">
      <div class="col-sm-8 col-sm-offset-2">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h2 class="panel-title">Too Doo List (5)</h2>
          </div>
          <ul class="list-group">
            <li class="list-group-item">
              <label class="form-check-label">
                <input class="form-check-input" type="checkbox" value="">
                Build
              </label>
            </li>
            <li class="list-group-item">
              <label class="form-check-label">
                <input class="form-check-input" type="checkbox" value="">
                A
              </label>
            </li>
            <li class="list-group-item">
              <label class="form-check-label">
                <input class="form-check-input" type="checkbox" value="">
                Todo
              </label>
            </li>
            <li class="list-group-item">
              <label class="form-check-label">
                <input class="form-check-input" type="checkbox" value="">
                List
              </label>
            </li>
            <li class="list-group-item">
              <label class="form-check-label">
                <input class="form-check-input" type="checkbox" value="">
                {{ message }}
              </label>
            </li>
          </ul>
          <div class="panel-heading">
            <h3 class="panel-title">Done List (2)</h3>
          </div>
          <ul class="list-group">
            <li class="list-group-item">
              <label class="form-check-label done">
                <input class="form-check-input" type="checkbox" value="" checked>
                Allow
              </label>
            </li>
            <li class="list-group-item">
              <label class="form-check-label done">
                <input class="form-check-input" type="checkbox" value="" checked>
                Complete
              </label>
            </li>
          </ul>
          <div class="panel-footer">
            <input type="text" class="form-control" placeholder="Type in new item...">  
            <a href="#" class="btn btn-large btn-block btn-primary">Add item</a>
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
      message: "Hello Vue!"
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
