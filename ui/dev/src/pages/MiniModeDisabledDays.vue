<template>
  <div class="row justify-center q-pa-md q-gutter-sm" style="max-width: 800px; width: 100%;">
    <q-calendar
      ref="calendar"
      v-model="selectedDate"
      view="month"
      bordered
      :disabled-days="disabledDays"
      mini-mode
      :day-style="modifiedStyle"
      locale="en-us"
      style="max-width: 300px; min-width: auto; overflow: hidden"
    />
    <q-calendar
      ref="calendar"
      v-model="selectedDate"
      view="month"
      bordered
      :disabled-days="disabledDays2"
      mini-mode
      :day-style="modifiedStyle"
      locale="en-us"
      style="max-width: 300px; min-width: auto; overflow: hidden"
    />
  </div>
</template>

<script>
export default {
  data () {
    return {
      selectedDate: '2019-04-01',
      disabledDays: [
        '2019-04-02',
        '2019-04-03',
        '2019-04-04',
        '2019-04-05'
      ],
      disabledDays2: [[
        '2019-04-02',
        '2019-04-05'
      ]]
    }
  },
  methods: {
    modifiedStyle (scope) {
      if (scope.disabled === true) {
        return {
          backgroundColor: '#ffcb9c!important',
          cursor: 'not-allowed'
        }
      }
      return {}
    }
  }
}
</script>
