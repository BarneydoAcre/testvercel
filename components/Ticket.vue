<template>
    <div id="Ticket">
        <Filters />
        <Action />
        <Data />
        <Table />
        <NovoTicket />
    </div>
</template>

<script>
import Table from '/components/Table.vue';
import Data from '/components/Data.vue';
import Filters from '/components/Filters.vue';
import Action from '/components/Action.vue';
import NovoTicket from '/components/NovoTicket.vue';

export default {
    name: 'Ticket',
    props: {},
    components: {
        Filters,
        Action,
        Table,
        Data,
        NovoTicket
    },
    data () {
        return {

        }
    }
}
</script>

<style scoped>
* {
}
#Ticket {
    display: grid;
    grid-template-columns: 60px repeat(3, calc(33.33% - 20px));
    grid-template-rows: 10vh 30vh 60vh;
    grid-template-areas: 
    "action action action data"
    "filter filter filter data"
    "table  table  table  table";

    /* grid-template-columns: 3fr 2fr;
    grid-template-rows: 3fr 6fr;
    grid-template-areas: 
    "filter action"
    "ticket ticket"; */

    background-color: white;
    width: inherit;
    height: inherit;
}
#Action {
    grid-area: action;
    margin: 16px 8px 8px 16px;
    filter: drop-shadow(0 4px 4px #9e9e9e);
}
#Data {
    grid-area: data;
    margin: 16px 16px 16px 8px;
    filter: drop-shadow(0 4px 4px #9e9e9e);
}
#Filter {
    grid-area: filter;
    margin: 8px 8px 16px 16px;
    filter: drop-shadow(0 4px 4px #9e9e9e);
}
#Table {
    grid-area: table;
    margin: 16px 16px 16px 16px;
    filter: drop-shadow(0 4px 4px #9e9e9e);
}
</style>