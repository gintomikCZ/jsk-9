<template>
  <h1>jsk-9</h1>
  <TTable
    :headers="['jméno', 'pozice', 'mzda']"
    :tableData="employees"
  />
  <div style="margin: 30px">
    <TInput
      label="jméno"
      control="firstname"
      @has-input="onHasInput"
    />
    <TInput
      label="příjmení"
      control="lastname"
      @has-input="onHasInput"
    />
    <TInput
      label="věk"
      control="age"
      inputType="number"
      @has-input="onHasInput"
    />
  </div>

  <TButton label="submit" size="small" @clicked="onBtnClicked" />
  <TList
    :items="['hruška', 'jablko', 'banán']"
    clickable
    @clicked="onListClicked"
  />
  <TList
    :items="['mrkev', 'celer', 'petržel']"
  />

</template>

<script>
import TButton from '@/components/TButton.vue'
import TList from '@/components/TList.vue'
import TTable from '@/components/TTable.vue'
import TInput from '@/components/TInput.vue'
export default {
  name: 'App',
  data () {
    return {
      employees: [
        { name: 'Karel', position: 'driver', salary: 54000 },
        { name: 'Jana', position: 'secretary', salary: 3000 },
        { name: 'Eva', position: 'manager', salary: 250 },
      ]
    }
  },
  methods: {
    onBtnClicked () {
      console.log('clicked')
    },
    onListClicked (par) {
      console.log(par)
    },
    onHasInput (payload) {
      console.log('kontrolka ' + payload.control + ' má hodnotu ' + payload.value)
    }
  },
  components: { TButton, TList, TTable, TInput }
}

</script>