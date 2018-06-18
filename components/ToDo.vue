<template>
  <div class="todo">
    <div class="todo__input">
      <input v-model="newTask" @keyup.enter="addTask">
    </div>

    <ul class="todo__list">
      <li
        class="todo-item"
        v-for="t in tasks"
        :key="t"
      >
        <div class="todo-item__text">{{ t }}</div>
        <button
          class="todo-item__button"
          @click="removeTask(t)"
        >
          remove
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
  data() {
    return {
      newTask: '',
      tasks: []
    }
  },
  methods: {
    addTask() {
      let task = this.newTask.trim()
      if (task) {
        this.tasks.push(task)
      }
      this.newTask = ''
    },
    removeTask(task) {
      let index = this.tasks.indexOf(task)
      console.log(task, index);
      this.tasks.splice(index, 1)
    }
  }
}
</script>

<style lang="sass">
.todo
  background: #fff
  width: 100%
  max-width: 960px
  border: 1px solid rgba(0,0,0,.1)
  &__input
    input
      width: 100%
      height: 44px
      padding: 0 12px
      font-size: 14px
      border: none
      &:focus
        outline: none
        border: 1px solid rgba(0,0,0,.2)
  &__list
    list-style-type: none
    padding: 0
.todo-item
  background: #fff
  width: 100%
  border-top: 1px solid rgba(0,0,0,.1)
  min-height: 44px
  padding: 0 12px
  display: flex
  justify-content: space-between
  align-items: center
  &__button
    background: none
    padding: 0
    height: auto
    border: none
    outline: none
    font-size: 12px
    font-style: italic
    cursor: pointer
    transition: opacity .25s ease-in-out
    &:hover
      opacity: .5
</style>
