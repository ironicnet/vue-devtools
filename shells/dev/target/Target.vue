<template>
  <div id="target">
    <h1>{{localMsg}}</h1>
    <span>Regex: {{regex.toString()}}</span>
    <input @keyup.enter="regex = new RegExp($event.target.value)"/>
    <span>(Press enter to set)</span>
    <br/>
    <button class="add" @click="add">Add</button>
    <button class="remove" @click="rm">Remove</button>
    <input v-model="localMsg">
    <other v-for="item in items" :key="item"></other>
  </div>
</template>

<script>
import Other from './Other.vue'
import MyClass from './MyClass.js'
export default {
  components: { Other },
  props: {
    msg: String,
    obj: null,
    ins: MyClass
  },
  data () {
    return {
      localMsg: this.msg,
      items: [1, 2],
      regex: /(a\w+b)/g,
      nan: NaN,
      infinity: Infinity
    }
  },
  computed: {
    awww () {
      return {
        a: {
          b: {
            c: 123
          }
        }
      }
    }
  },
  methods: {
    add () {
      this.items.push(1, 2, 3)
    },
    rm () {
      this.items.pop()
    }
  }
}
</script>
