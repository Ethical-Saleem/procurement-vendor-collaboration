<template>
  <Header>
    <template #brand>
      <span class="navbar-brand text-white"><i class="fa-solid fa-house"></i></span>
      <span class="navbar-text title text-white">
        <router-link :to="{name: 'admin-dashboard'}">
          PROCUREMENT ADMIN PORTAL
        </router-link>
      </span>
    </template>
  </Header>
  <navbar></navbar>
  <div class="main-content">
    <div class="container-fluid">
      <div class="table-responsive my-4">
        <b-table
      responsive
      hover
      bordered
      :fields="fields"
      :items="purchaseOrders"
      >
      <template #cell(purchase_code)="data">
        <div class="">
          <router-link class="route-link" :to="{ name: 'PurchaseOrderDetail', params:{purchase_code: data.item.purchase_code} }">
            {{data.item.purchase_code}}
          </router-link>
        </div>
      </template>
      <template #cell(description)="data">
        <div class="">
          {{data.item.description}}
        </div>
      </template>
      <template #cell(posting_date)="data">
        <div class="">
          {{data.item.posting_date}}
        </div>
      </template>
      <template #cell(order_date)="data">
        <div class="">
          {{data.item.order_date}}
        </div>
      </template>
      <template #cell(status)="data">
        <div class="">
          {{data.item.status}}
        </div>
      </template>
      </b-table>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/admin/AdminHeader.vue'
import Navbar from '@/components/admin/AdminNavBar.vue'

export default {
  name: 'purchase-order',
  components: {
    Header,
    Navbar
  },
  data () {
    return {
      fields: [
        {
          key: 'purchase_code',
          label: 'PURCHASE CODE',
          sortable: true
        },
        {
          key: 'description',
          label: 'POSTING DESCRIPTION',
          sortable: true
        },
        {
          key: 'posting_date',
          label: 'POSTING DATE',
          sortable: true
        },
        {
          key: 'order_date',
          label: 'ORDER DATE',
          sortable: true
        },
        {
          key: 'status',
          label: 'STATUS',
          sortable: true
        }
      ],
      purchaseOrders: [
        {
          purchase_code: 'PO220221',
          description: 'Supply of Laptops',
          posting_date: '2022-01-28',
          order_date: '2022-02-05',
          status: 'Accepted'
        },
        {
          purchase_code: 'PO423547',
          description: 'Supply of Stationaries',
          posting_date: '2022-01-28',
          order_date: '2022-02-05',
          status: 'Pending'
        },
        {
          purchase_code: 'PO423092',
          description: 'Supply of Printers',
          posting_date: '2022-01-28',
          order_date: '2022-02-05',
          status: 'Accepted'
        },
        {
          purchase_code: 'PO421010',
          description: 'Supply of Toileteries',
          posting_date: '2022-01-28',
          order_date: '2022-02-05',
          status: 'Pending'
        },
        {
          purchase_code: 'PO423548',
          description: 'Supply of Furnitures',
          posting_date: '2022-01-28',
          order_date: '2022-02-05',
          status: 'Accepted'
        }
      ]
    }
  }
}
</script>

<style scoped>
.route-link {
  text-decoration: none;
  color: #000;
}
</style>
