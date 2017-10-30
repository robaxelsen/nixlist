<template>
  <div class="nixlist">
    <h4>Welcome to NixList</h4>
    <h5>Your Unix and Linux Command Resource</h5>
    <ul>
        <li v-for="command in commands" :key="command.title">
            {{ command.title }}
        </li>
    </ul>
    <div>
	<q-card v-for="command in commands" :key="command.title" inline style="width: 500px">
	    <h3>{{ command.title }}</h3>
	    <p>{{ command.description }}</p>
	</q-card>
    </div>
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
