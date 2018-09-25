<template>
  <div>
    <md-dialog-confirm
      :md-active.sync="active"
      md-title="Do You Really Want To Delete this Profile?"
      md-content="This will be <strong>Permanently Deleted</strong>."
      md-confirm-text="Yes"
      md-cancel-text="No"
      @md-cancel="onCancel"
      @md-confirm="onConfirm" />
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="ID Number">{{ item.user_id }}</md-table-cell>
        <md-table-cell md-label="Name">{{ item.name + item.name2 + item.name3 }}</md-table-cell>
        <md-table-cell md-label="Email">{{ item.email }}</md-table-cell>
        <md-table-cell md-label="Contact Number">{{ item.number }}</md-table-cell>
        <md-table-cell md-label="User Type">{{ item.user_type }}</md-table-cell>
        <md-table-cell md-label="Action">
          <md-button  class="md-just-icon md-simple md-primary" @click="active = true">
            <md-icon>delete_forever</md-icon>
            <md-tooltip md-direction="bottom">Delete</md-tooltip>
          </md-button>
        </md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: 'it-department',
  props: {
    tableHeaderColor: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      active: false,
      selected: [],
      users: [
        {
          user_id: '17 - 12456',
          name: 'Ivan',
          name2: ' David',
          name3: ' Badbaden',
          email: 'ivanbadbaden@gmail.com',
          number: '09773798525',
          user_type: 'Faculty Researcher'
        },
        {
          user_id: '17 - 16267',
          name: 'Anjeanette',
          name2: ' Jane',
          name3: ' Francia',
          email: 'aj.francia@gmail.com',
          number: '09773798526',
          user_type: 'Faculty Researcher'
        },
        {
          user_id: '17 - 14598',
          name: 'Nomar',
          name2: ' Pauco',
          name3: ' Lapitan',
          email: 'nom.lapitan@gmail.com',
          number: '09216144974',
          user_type: 'Faculty Researcher'
        },
        {
          user_id: '17 - 42681',
          name: 'Isaiah',
          name2: ' Dizon',
          name3: ' Cruz',
          email: 'ice.cruz@gmail.com',
          number: '09216144987',
          user_type: 'Faculty Researcher'
        },
        {
          user_id: '17 - 48631',
          name: 'Jo',
          name2: ' Anne',
          name3: ' Cura',
          email: 'jo.annecura@gmail.com',
          number: '09773798527',
          user_type: 'Department Research Chairperson'
        }
      ]
    }
  },
  methods: {
    onConfirm () {
      this.value = 'Agreed'
    },
    onCancel () {
      this.value = 'Disagreed'
    }
  }
}
</script>
