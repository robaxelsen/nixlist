<template>
  <div class="nixlist">
    <h4>Welcome to NixList</h4>
    <h5>Your Unix and Linux Command Resource</h5>
    <div class="layout-padding nix-card row items-start relative-position">
	<q-card v-for="command in commands" :key="command.title" inline class="bigger">
            <q-card-title>
                <h3>{{ command.title }}</h3>
            </q-card-title>
            <q-card-separator />
            <q-card-main>
                <p>{{ command.description }}</p>
            </q-card-main>
	    <q-card-actions align="center">
		<q-btn flat round small><q-icon name="launch" /></q-btn>
	    </q-card-actions>
	</q-card>
    </div>
  </div>
</template>

<script>
import { QCard, QBtn, QCardMain, QCardTitle, QCardSeparator, QCardActions, QIcon } from 'quasar'
export default {
  data () {
    return {
      commands: [
        { title: 'awk', description: 'description goes here' },
        { title: 'cat', description: 'description goes here' },
        { title: 'cd', description: 'description goes here' },
        { title: 'grep', description: 'description goes here' },
        { title: 'ip', description: 'description goes here' },
        { title: 'ls', description: 'description goes here' },
        { title: 'sed', description: 'description goes here' },
        { title: 'tar', description: 'description goes here' },
        { title: 'top', description: 'description goes here' }
      ]
    }
  },
  name: 'nixlist',
  components: {
    QCard,
    QBtn,
    QCardMain,
    QCardTitle,
    QCardSeparator,
    QCardActions,
    QIcon
  }
}
</script>

<style lang="stylus">
@import '~variables'

.nixlist
  margin-top 50px
  a
    color #35495E
ul
  list-style-type none
  padding 0
.nix-card
  .q-card
    width 300px
  .bigger
    width 450px
  @media (max-width $breakpoint-xs-max)
    .q-card
      width 100%
</style>
