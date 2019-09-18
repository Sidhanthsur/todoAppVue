<template>
  <div class="home">
    <b-button @click="clickMe">Add Board +</b-button>
    <hr />
    <ul
      v-for='board in boards'
      :key="board._id"
    >
      <li>
        <Board :board='board' />
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src
import Board from '@/components/Board.vue'
import db from '@/db/index.js'

export default {
  name: 'home',
  data: function () {
    return {
      boards: []
    }
  },
  components: {
    Board
  },
  computed: {

  },
  created () {

  },
  methods: {
    clickMe () {
      var doc = {
        _id: new Date().toLocaleString(),
        name: 'trial'
      }
      db.put(doc)
      this.boards.push(doc)
    }
  }
}
</script>
