<template>
<div class="nixlist">
<h4>NixList</h4>
<h5>Unix/Linux Commands</h5>
<q-card v-for="command in commands" :key="command.title" class="command-card">
    <q-collapsible icon="star_border" :label="command.title">
        <ul>
            <li><strong>Description:</strong> {{ command.description }}</li>
        </ul>
    </q-collapsible>
    <q-card-separator />
    <q-card-actions align="center">
        <q-btn flat round small><q-icon name="launch" /></q-btn>
    </q-card-actions>
</q-card>
</div>
</template>

<script>
import { QCard, QBtn, QCardMain, QCardTitle, QCardSeparator, QCardActions, QCollapsible, QIcon } from 'quasar'
export default {
    data() {
        return {
            commands: [{
                title: 'awk',
                description: 'description goes here'
            },
            {
                title: 'cat',
                description: 'description goes here'
            },
            {
                title: 'cd',
                description: 'description goes here'
            },
            {
                title: 'grep',
                description: 'description goes here'
            },
            {
                title: 'ip',
                description: 'description goes here'
            },
            {
                title: 'ls',
                description: 'description goes here'
            },
            {
                title: 'sed',
                description: 'description goes here'
            },
            {
                title: 'tar',
                description: 'description goes here'
            },
            {
                title: 'top',
                description: 'description goes here'
            }
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
        QCollapsible,
        QIcon
    }
}
</script>

<style lang="stylus">
@import '~variables'

.command-card
  padding 15px
.nixlist
  margin 0 auto
  max-width 1200px
  margin-top 40px
  a
    color #35495E
  h5
    margin-bottom 50px
ul
  list-style-type none
  padding 0
</style>
