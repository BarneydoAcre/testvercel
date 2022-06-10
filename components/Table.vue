<template>
    <div id="Table">
        <table id="Table_t">
            <thead id="Table_header">
                <tr id="Table_header_row">
                    <th id="Table_header_id">id</th>
                    <th id="Table_header_assunto">Assunto</th>
                    <th id="Table_header_status">Status</th>
                    <th id="Table_header_tempo">Tempo</th>
                </tr>
            </thead>
            <tbody id="Table_header">
                <tr id="Table_data_row" v-for="t in tickets" :key="t.id">
                    <td id="Table_data_id">#{{ t.id }}</td>
                    <td id="Table_data_assunto">{{ t.assunto }}</td>
                    <td id="Table_data_status">{{ t.status }}</td>
                    <td id="Table_data_tempo">{{ t.tempo }}</td>
                </tr>
            </tbody>
        </table>
        </div>
</template>

<script>
export default {
    name: 'Table',
    data () {
        return {
            tickets: [{
                id: '00001', 
                assunto: 'Ajuda com emissão de nota fiscal', 
                status: 'Em Atendimento', 
                tempo:'1 hora e 30 minutos'
                },
                {
                id: '00002', 
                assunto: 'Problema com impressora', 
                status: 'Finalizado', 
                tempo:'27 minutos'
                },
            ],
        }
    }
}
</script>

<style scoped>
#Table {
    background-color: rgb(216,216,216);
    border-radius: 5px 5px 5px 5px;
    overflow-y: scroll;
}
#Table_t {
}

th, td {
    border-collapse: collapse;
    border: 1px solid rgb(216,216,216);
    
}
#Table thead th{
    background-color: rgb(146, 146, 146);
    border-radius: 5px 5px 5px 5px;
    position: sticky;
    top: 0;
}
#Table tbody td{
    background-color: rgb(191, 191, 191);
    border-radius: 5px 5px 5px 5px;
}
#Table thead th,
#Table tbody td {
    padding: 10px;
    text-align: center;
    height: 40px;
}
#Table_header_id,
#Table_data_id {
    width: 10%;
    text-align: center;
}
#Table_header_assunto,
#Table_data_assunto {
    width: 60%;
    text-align: center;
}
#Table_header_status,
#Table_data_status {
    width: 20%;
    text-align: center;
}
#Table_header_tempo,
#Table_data_tempo {
    width: 10%;
    text-align: center;
}
</style>