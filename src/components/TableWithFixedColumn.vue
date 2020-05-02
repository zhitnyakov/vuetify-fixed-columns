<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">

        <v-data-table
          :headers="cols"
          :items="items"
          fixed-header
          :items-per-page="10"
          :height="400"
          disable-pagination
          hide-default-footer
          class="elevation-1"
        >

        <template #body="">
            <tbody>
              <tr
                v-for="a in 100"
                :key="`row-${a}`"
              >
              <td v-for="b in 20" :key="`row-${a}-cell-${b}`">
                <div>row{{a}}</div>
                <div>column{{b}}</div>
              </td>
              </tr>
            </tbody>
          </template>

        </v-data-table>

      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'TableWithFixedColumn',

    computed: {
      cols() {
        let cols = [];
        for (let i = 1; i <= 20; i++) {
          cols.push({
                        text: `Column ${i}`,
                        value: `column-${i}`,
                        width: 100
                    })
        }
        return cols;
      }
    }
  }
</script>
<style>
  table > tbody > tr > td:nth-child(1), 
  table > thead > tr > th:nth-child(1) {
    position: sticky !important; 
    position: -webkit-sticky !important; 
    left: 0; 
    z-index: 9998;
    background: white;
  }

  table > thead > tr > th:nth-child(1) {
    z-index: 9999;
  }
</style>
