<template>
  <div>
    <Breadcrumbs main="" title="Inventory"/>
    <!-- Container-fluid starts-->
    <div class="container-fluid pos_custom_table">
        <b-card header-tag="div" no-body>
            <b-card-body>
                <b-tabs pills slot="header" class="tabbed-card border-tab nav-primary">
                    <b-tab title="Income">
                        <template slot="title">
                            Groups
                        </template>
                        <b-card-text>
                            <div class="row">
                                <div class="card-body">
                                    <div class="datatable-vue m-0">
                                        <a @click="quickView" class="new_order_link">New Group</a>
                                        <div class="table-responsive vue-smart">
                                            <v-table
                                                :data="users.data" class="table"
                                                :currentPage.sync="filter.currentPage"
                                                :pageSize="10"
                                                @totalPagesChanged="filter.totalPages = $event"
                                                :filters="filters"
                                            >
                                                <thead slot="head">
                                                    <v-th sortKey="name">Name</v-th>
                                                    <v-th sortKey="position">Total Members</v-th>
                                                </thead>
                                                <tbody slot="body" slot-scope="{displayData}">
                                                    <tr v-for="row in displayData" :key="row.id">
                                                        <td>{{ row.name }}</td>
                                                        <td>{{ row.age }}</td>
                                                        <td>
                                                            <b-button-group>
                                                                <b-dropdown left text="Operations" variant="light">
                                                                    <b-dropdown-item variant="primary">View</b-dropdown-item>
                                                                    <b-dropdown-item variant="secondary">Edit</b-dropdown-item>
                                                                    <b-dropdown-item variant="danger"> Remove</b-dropdown-item>
                                                                </b-dropdown>
                                                            </b-button-group>
                                                        </td>
                                                    </tr>
                                                </tbody>
                                            </v-table>
                                        </div>
                                        <smart-pagination
                                            :currentPage.sync="filter.currentPage"
                                            :totalPages="filter.totalPages"
                                        />
                                    </div>
                                </div>
                            </div>
                        </b-card-text>
                    </b-tab>
                    <b-tab title="Members">
                        <template slot="title">
                            Members
                        </template>
                        <b-card-text>
                            <div class="row">
                                <div class="card-body">
                                    <div class="datatable-vue m-0">
                                        <a @click="quickView" class="new_order_link">New Member</a>
                                        <div class="table-responsive vue-smart">
                                            <v-table
                                                :data="users.data" class="table"
                                                :currentPage.sync="filter.currentPage"
                                                :pageSize="10"
                                                @totalPagesChanged="filter.totalPages = $event"
                                                :filters="filters"
                                            >
                                                <thead slot="head">
                                                    <v-th sortKey="name">Name</v-th>
                                                    <v-th sortKey="position">Group</v-th>
                                                </thead>
                                                <tbody slot="body" slot-scope="{displayData}">
                                                    <tr v-for="row in displayData" :key="row.id">
                                                        <td>{{ row.name }}</td>
                                                        <td>{{ row.age }}</td>
                                                        <td>
                                                            <b-button-group>
                                                                <b-dropdown left text="Operations" variant="light">
                                                                    <b-dropdown-item variant="primary">View</b-dropdown-item>
                                                                    <b-dropdown-item variant="secondary">Edit</b-dropdown-item>
                                                                    <b-dropdown-item variant="danger"> Remove</b-dropdown-item>
                                                                </b-dropdown>
                                                            </b-button-group>
                                                        </td>
                                                    </tr>
                                                </tbody>
                                            </v-table>
                                        </div>
                                        <smart-pagination
                                            :currentPage.sync="filter.currentPage"
                                            :totalPages="filter.totalPages"
                                        />
                                    </div>
                                </div>
                            </div>
                        </b-card-text>
                    </b-tab>
                </b-tabs>
            </b-card-body>
        </b-card>
    </div>
    <!-- Container-fluid Ends-->
    <!-- QuickView Modal -->
    <b-modal size="lg" centered v-model="modalShow" hide-footer hide-header>
        <button class="close" type="button" v-on:click="quickViewClose(modalShow)">
            <span>×</span>
        </button>
        <div class="col-sm-12">
            <h5 class="mb-0">New Group</h5>
        </div>
        <b-form class="needs-validation">
            <div class="form-row">
                <div class="col-md-6">
                    <label for="browser_first_name">New Group Name</label>
                    <b-form-input type="text" id="browser_first_name" required placeholder="Group name"></b-form-input>
                </div>
                <div class="col-md-6 m-t-3">
                    <label for="browser_last_name">Existing Groups</label>
                    <b-form-select 
                        class="form-control"
                        v-model="supported_form.selected" 
                        :options="supported_form_select_options" 
                        :state="supported_select_state"
                    >
                    </b-form-select>
                </div>
            </div>
            <div class="col-sm-12">
                <h5 class="mb-0">Permissions</h5>
            </div>
            <div class="form-row">
                <div class="form-group checkbox col-sm-6">
                    <div class="checkbox checkbox-dark">
                        <b-form-checkbox name="checkbox7" >Option 1</b-form-checkbox>
                    </div>
                    <div class="checkbox checkbox-dark">
                        <b-form-checkbox name="checkbox8">Option 2</b-form-checkbox>
                    </div>
                    <div class="checkbox checkbox-dark">
                        <b-form-checkbox name="checkbox9">Option 3</b-form-checkbox>
                    </div>
                </div>
                <div class="form-group checkbox col-sm-6">
                    <div class="checkbox checkbox-dark">
                        <b-form-checkbox name="checkbox7" >Option 1</b-form-checkbox>
                    </div>
                    <div class="checkbox checkbox-dark">
                        <b-form-checkbox name="checkbox8">Option 2</b-form-checkbox>
                    </div>
                    <div class="checkbox checkbox-dark">
                        <b-form-checkbox name="checkbox9">Option 3</b-form-checkbox>
                    </div>
                </div>
            </div>

            <b-button type="submit" variant="primary">Submit Form</b-button>
        </b-form>
    </b-modal>
  </div>
</template> 
<script>
import { mapState, mapGetters } from 'vuex';
import users from '../../data/users';
  
  export default {
    name:'Member',
    components: {
    },
    data(){
      return{
        users,
        counter: 1,
        modalShow: false,
        filter:{
          currentPage: 1,
          totalPages: 0,
        },
        filters: {
          name: { value: '', keys: ['name'] },
          position: { value: '', keys: ['position'] },
          office: { value: '', keys: ['office'] },
          age: { value: '', keys: ['age'] },
          startdate: { value: '', keys: ['startdate'] },
          salary: { value: '', keys: ['salary'] },
        },
        supported_form:{
          checkbox:false,
          radio:null,
          selected: null,
          file:null
        },
        supported_form_select_options: [
          { value: null, text:'Current Group Names' },
          { value: '1', text:'One' },
          { value: '2', text:'Two' },
          { value: '3', text:'Three' },
        ],
        supported_form_radio_options: [
          { text: 'Toggle this custom radio', value: 'first' },
          { text: 'Or toggle this other custom radio', value: 'second' }
        ],
      };
    },
    computed: {
      ...mapState({
        cart: state => state.products.cart,
        getAmount() {
          return this.totalAmount = this.$store.getters['products/getTotalAmount'];
        }
      })
    },
    methods: {
      getImgUrl(path) {
        return require('../../assets/images/'+path);
      },
      removeProduct: function(product) {
        this.$store.dispatch('products/removeProduct', product);
      },
      increment(product,qty=1) {      
        this.$store.dispatch('products/updateCartQuantity', { 'product':product,'qty':qty });
      },
      decrement(product,qty = -1) {
        this.$store.dispatch('products/updateCartQuantity', { 'product':product,'qty':qty });
      },
      setactiveemails(id) {
        this.editorShow = !this.editorShow;
        this.$store.dispatch('email/setactiveemails',id);
      },
      
      //Quick View
      quickView: function() {
        this.modalShow = true;
      },
      quickViewClose: function() {
        this.modalShow = false;
      },

    }
  };
</script>