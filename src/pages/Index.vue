<template>
  <q-page padding>
     <q-table
      title="Jadwal Pesawat DesAn"
      :data="data"
      :columns="columns"
      row-key="name"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="waktu" :props="props">
            {{ props.row.waktu }}
          </q-td>
          <q-td key="tujuan" :props="props">
            {{ props.row.tujuan }}
          </q-td>
          <q-td key="harga" :props="props">
            {{ props.row.harga }}
          </q-td>
          <q-td key="aksi" :props="props">
            <div class="row">
              <div class="col">
                <q-btn label="Edit" color="green" icon="edit" unelevated></q-btn>
              </div>
              <div class="col">
                <q-btn label="Hapus" color="negative" icon="delete" unelevated></q-btn>
              </div>
            </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      columns: [
        {
          name: 'waktu',
          required: true,
          label: 'Waktu',
          align: 'left',
          field: 'waktu',
          sortable: true
        },
        { name: 'tujuan', align: 'center', label: 'Tujuan', field: 'tujuan', sortable: true },
        { name: 'harga', label: 'Harga', align: 'center', field: 'harga', sortable: true },
        { name: 'aksi', label: 'Aksi', field: 'aksi', align: 'center' }
      ],

      data: [
        {
          waktu: '2 Mei 2020, 17:00',
          tujuan: 'LPG-JKT',
          harga: '399.000'
        },
        {
          waktu: '28 Mei 2020, 05:00',
          tujuan: 'JKT-MLY',
          harga: '899.000'
        },
        {
          waktu: '10 JUni 2020, 11:00',
          tujuan: 'LPG-DNP',
          harga: '799.000'
        },
        {
          waktu: '2 Mei 2020, 10:00',
          tujuan: 'LPG-MDN',
          harga: '499.000'
        }
      ]
    }
  }
}
</script>
