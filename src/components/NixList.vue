<template>
  <div class="nixlist">
    <h4>Welcome to NixList</h4>
    <h5>Your Unix and Linux Command Resource</h5>
    <ul>
        <li v-for="command in commands">
            {{ command.title }}
        </li>
    </ul>
    <q-card v-for="command in commands">
        <q-card-title>{{ command.title }}</q-card-title>
        <q-card-separator />
        <q-card-main>{{ command.description }}</q-card-main>
    </q-card>
  </div>
</template>

<script>
import { QCard } from 'quasar'
export default {
  data () {
    return {
      commands: [
        { title: 'awk', description: 'description goes here' },
        { title: 'cat', description: 'description goes here' },
        { title: 'grep', description: 'description goes here' },
        { title: 'sed', description: 'description goes here' }
      ]
    }
  },
  name: 'nixlist',
  components: {
    QCard
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus">
@import '~variables'

.nixlist
  margin-top 50px
  a
    color #35495E

ul
  list-style-type none
  padding 0

</style>
