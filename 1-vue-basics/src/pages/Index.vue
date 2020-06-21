<template>
  <q-page padding>
    <button
      style="position: absolute; right: 10px"
      @click="count++"
    >
      {{ count }}
    </button>

    <input
      v-model="message"
      @keyup="handleKeyup"
      @keyup.enter="alertMessage"
      v-autofocus
      :class="{'error': message.length > 22}"
      ref="messageInput"
    />
    <button @click="clearMessage">Clear</button>

    <div>Message length: {{ message.length }}</div>

    <h5
      class="border-gray"
      v-if="message.length"
    >{{ message }}</h5>
    <h6 v-else>No message entered 😂</h6>

    <hr>

    <p>Uppercase message: {{ messageUpperCase }} </p>
    <p>Lowercase message:{{ message | messageLowerCase }} </p>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      message: 'I love Vue.js!',
      count: 0
    }
  },
  computed: {
    messageUpperCase () {
      console.log('messageUpperCase was fired')
      return this.message.toUpperCase()
    }
  },
  methods: {
    clearMessage () {
      this.message = ''
    },
    handleKeyup (event) {
      if (event.keyCode === 27) {
        this.clearMessage()
      }
    },
    alertMessage () {
      alert(this.message)
    },
    errorStyle () {
      return { error: this.message.length > 22 }
    }
  },
  filters: {
    messageLowerCase (val) {
      return val.toLowerCase()
    }
  },
  directives: {
    autofocus: {
      inserted (element) {
        element.focus()
      }
    }
  },
  beforeCreate () {
    console.log('before create')
  },
  created () {
    console.log('created')
  },
  beforeMount () {
    console.log('before mount')
  },
  mounted () {
    console.log('this.$refs', this.$refs)
    // {messageInput: input}
    this.$refs.messageInput.className = 'bg-green'
    console.log('mounted')
  },
  beforeUpdate () {
    console.log('before update')
  },
  updated () {
    console.log('updated')
  },
  beforeDestroy () {
    console.log('before destroy')
  },
  destroyed () {
    console.log('destroyed')
  }

}
</script>

<style>
.border-gray {
  border: 1px solid gray;
}
input,
button {
  font-size: 23px;
}
.error {
  color: red;
  background: pink;
}
</style>
