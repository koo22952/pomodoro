<template>
  <section class="home-left__add" :class="{'wordColor':isbreakTime}">
    <input v-model="inputValue" @keyup.13="onAddList" placeholder="add a new mission…" />
    <i class="material-icons" @click="onAddList">add</i>
  </section>
</template>

<script>
  export default {
    props: ['isbreakTime'],
    data() {
      return {
        inputValue: ''
      }
    },
    methods: {
      onAddList() {
        if (this.inputValue === '') {
          return
        }

        this.$emit('onAddList', this.inputValue)
        this.inputValue = ''

      }
    }
  }
</script>


<style lang="scss" scoped>
  $lightColor: #ff4384;
  $lightBg: #ffedf7;
  $darkColor: #00a7ff;
  $darkBg: #e5f3ff;

  .home-left__add {
    height: 56px;
    width: 445px;
    color: $lightColor;
    position: relative;
    font-style: italic;
    font-weight: bold;

    input {
      height: 100%;
      width: 100%;
      padding: 0px 16px;
      font-size: 16px;
      border: none;
      color: $lightColor;
      font-style: italic;
      font-weight: bold;
      text-transform: uppercase;
    }
    i {
      position: absolute;
      cursor: pointer;
      top: 50%;
      right: 16px;
      transform: translate(0, -50%);
    }
    ::placeholder {
      font-size: 16px;
      font-weight: bold;
      font-style: italic;
      color: $lightColor;
    }
  }

  .wordColor {
    color: $darkColor;
    input {
      color: $darkColor;
    }
    ::placeholder {
      color: $darkColor;
    }
  }
</style>
