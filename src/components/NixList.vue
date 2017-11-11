<template>
<div class="nixlist">
    <h4>NixList</h4>
    <h5>Unix/Linux Commands</h5>
    <q-input inverted clearable :v-model="input" float-label="Search" id="input" color="primary" :before="[{ icon: 'search' }]" />
    <q-card v-for="(command, index) in commands" :key="command.title" class="command-card" :id="getId(index)">
        <q-collapsible :label="command.title" class="nix-collapse">
            <ul>
                <li><strong>Description:</strong> {{ command.description }}</li>
            </ul>
        </q-collapsible>
    </q-card>
</div>
</template>

<script>
import { QCard, QBtn, QCardMain, QCollapsible, QIcon, QInput } from 'quasar'
export default {
    name: 'nixlist',
    components: {
        QCard,
        QBtn,
        QCardMain,
        QCollapsible,
        QIcon,
        QInput
    },
    data() {
        return {
            input: '',
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
    methods: {
        getId(id) {
            return `card-${id}`;
        }
    }
}
</script>

<style lang="stylus">
@import '~variables'

.command-card
  padding 15px
  .nix-collapse
    .q-item-label
        font-size 22px
        text-align center
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
#input
    max-width 500px
    margin 0 auto
    margin-bottom 60px
    text-align left
</style>
