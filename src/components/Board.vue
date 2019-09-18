<template>
  <div>
    <h1>{{ board.name }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    board: {
      type: Object
    }
  }
}
</script>
