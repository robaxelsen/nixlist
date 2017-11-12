<template>
<div class="nixlist">
    <h4>NixList</h4>
    <h5>Unix/Linux Commands</h5>
    <q-search inverted autofocus color="secondary" v-model="search" placeholder="Search ..." id="search" align="left" />
    <q-card inverted color="tertiary" v-for="(command, index) in filteredItems" :key="command.title" class="command-card" :id="getId(index)">
        <q-collapsible :label="command.title" class="nix-collapse">
            <ul>
                <li><strong>Description:</strong> {{ command.description }}</li>
            </ul>
        </q-collapsible>
    </q-card>
	<q-btn
		v-back-to-top.animate="{offset: 500, duration: 200}"
		round
		color="secondary"
		class="fixed-bottom-right animate-pop"
		style="margin: 0 15px 15px 0">
		<q-icon name="keyboard_arrow_up" />
    </q-btn>
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
            search: null,
            commands
        }
    },
	computed: {
		filteredItems() {
			let commands = this.commands;
			if (!this.search) return commands;
			let searchValue = this.search.toLowerCase();
			let filter = command => command.title.toLowerCase().includes(searchValue);
			return commands.filter(filter);
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
        height 72px
        margin 0 7px 50px 7px
        font-size 22px
        .q-icon
            font-size 32px
</style>
