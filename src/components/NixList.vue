<template>
<div class="nixlist">
    <h4>NixList</h4>
    <h5>Unix/Linux Commands</h5>
    <q-search inverted color="primary" :v-model="input" placeholder="Search" id="search" value="">
    </q-search>
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
import { QCard, QBtn, QCardMain, QCollapsible, QIcon, QInput,
    QSearch } from 'quasar'
import commands from '../assets/data/commands.json'
export default {
    name: 'nixlist',
    components: {
        QCard,
        QBtn,
        QCardMain,
        QCollapsible,
        QIcon,
        QSearch
    },
    data() {
        return {
            input: '',
            commands
        }
    },
    methods: {
        getId(id) {
            return `card-${id}`;
        },
        search() {
            console.log('searching');
        }
    }
}
</script>

<style lang="stylus">
@import '~variables'

.nixlist
    margin 0 auto
    max-width 1200px
    margin-top 40px
    a
        color #35495E
    h5
        margin-bottom 50px
    .command-card
      padding 15px
      .nix-collapse
        .q-item-label
            font-size 22px
            text-align center
    ul
        list-style-type none
        padding 0
    #search
        text-align left
        margin 0 7px 50px 7px
        font-size 22px
        .q-icon
            font-size 32px
</style>
