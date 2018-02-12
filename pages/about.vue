<template>
  <section>
      <h1 :style="`color: ${color}`"> About</h1>
      <p>{{message}}</p>
      <p>lorem</p>
      <input type="text" v-model="color">

      <ul style="margin:20px; background-color: white;">
          <li v-for="(item, index) in list" :key="index" class="row" :class="`done-${item.done}`">
              <div class="column">
                <h6>message</h6>
                <span>{{item.message}}</span>
              </div>
              <button @click="toggleTodo(index)">{{item.done ? 'undone' : 'finish'}}</button>
              <button @click="removeTodo(index)">remove</button>
          </li>
      </ul>

      <hr>
      <input type="text" v-model="message" @keyup.enter="addTodo(message)">
      <button @click="addTodo(message)" :disabled="!message">Add</button>
    
  </section>
</template>

<script>
export default {
  data() {
      return {
          message: 'hello!',
          color: 'blue',
          list: [
              {done: true, message: 'hi there'},
              {done: true, message: 'how\'re you doin'}
            ]
      }
  },
  methods: {
      addTodo(mess) {
          this.list.push({
              done: false,
              message: mess
          })
          this.message = ''
      },
      removeTodo(index) {
          this.list.splice(index, 1)
      },
      toggleTodo(index) {
          this.list = this.list.map((item, itemIndex) => {
              const done = item.done
              return index !== itemIndex ? item : Object.assign({}, item, {done: !done})
          })
      }
  }
}
</script>

<style scoped>
.done-true {
    text-decoration: line-through;
}
.row {
    display: flex;
    width: 100%;
    flex-direction: row;
    padding: 4px 16px;
}
.column {
    display: flex;
    flex: 1;
    flex-direction: column;
}
button {
    display: block;
    width: 100px;
}
</style>

