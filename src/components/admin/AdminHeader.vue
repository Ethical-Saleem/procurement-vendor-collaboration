<template>
  <div class="navbar-header">
    <div class="navbar navbar-expand-sm navbar-dark h-100 py-0" id="firstNav">
      <!-- Container wrapper -->
      <div class="container-fluid h-100">
        <div class="container-fluid w-sm-75 px-0">
          <slot name="brand"></slot>
          <button class="navbar-toggler text-white ms-auto" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <i class="fa-solid fa-bars"></i>
          </button>
        </div>
        <!-- Collapsible wrapper -->
        <div class="collapse navbar-collapse w-50 h-100" id="navbarSupportedContent">
          <!-- Right links -->
          <ul class="navbar-nav w-100 h-100 mt-lg-0 d-flex" id="firstList">
            <li class="nav-item dropdown text-center mx-lg-1 h-100" id="navItem">
              <a class="nav-link dropdown-toggle text-white mt-2" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown"
              aria-expanded="false">
                <i class="fa-solid fa-circle-plus"></i>
              </a>
              <!-- Dropdown menu -->
              <ul class="dropdown-menu dropdown-menu-center border p-1" aria-labelledby="navbarDropdown" style="width:99%">
                <li>
                  <a href="" class="dropdown-item small" type="button" data-bs-toggle="modal"
                   data-bs-target="#newRequisition">
                    Create New Supplier
                  </a>
                </li>
                <li>
                  <a href="#" class="dropdown-item small" type="button">
                    Create New RFQ
                  </a>
                </li>
              </ul>
            </li>
            <li class="nav-item text-center mx-lg-1" id="navItem">
              <router-link to="/user-notifications" class="nav-link text-white mt-2">
                <i class="fas fa-bell fa-lg mb-1"></i>
              </router-link>
            </li>
            <li class="nav-item dropdown text-center mx-lg-1 text-white" id="navItem">
              <a class="nav-link dropdown-toggle text-white mt-2" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown"
              aria-expanded="false">
                <i class="fa-solid fa-user"></i>
              </a>
              <ul class="dropdown-menu dropdown-menu-center" aria-labelledby="navbarDropdown" style="width:99%;">
                <li>
                  <a href="#" class="dropdown-item small">
                   Admin Profile
                  </a>
                </li>
                <li>
                  <a href="#passwordReset" class="dropdown-item small" data-bs-toggle="modal">
                   Add New Admin User
                  </a>
                </li>
                <li>
                  <router-link to="/Sign-in" class="dropdown-item small">Sign out</router-link>
                </li>
              </ul>
            </li>
          </ul>
        </div>
      <!-- Collapsible wrapper -->
      </div>
    <!-- Container wrapper -->
    </div>
  </div>
  <div class="modal" tabindex="-1" id="newRequisition" aria-hidden="true">
    <div class="modal-dialog modal-lg">
      <div class="modal-content">
        <div class="modal-body new-requisition">
          <div class="">
            <div class="mx-4 mb-5 py-5">
              <p class="fw-bold text-center" style="font-size:20px">
                Add New Requisition
              </p>
              <div class="">
                <requisitionForm/>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="modal" tabindex="-1" id="passwordReset" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-body new-requisition">
          <div class="">
            <div class="mx-4 mb-2 py-3">
              <p class="fw-bold text-center" style="font-size:20px">
                User Password Change
              </p>
              <div class="">
                <password-reset></password-reset>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import requisitionForm from '@/components/RequisitionForm.vue'
import passwordReset from '@/components/PasswordChange.vue'
export default {
  name: 'nav-header',
  components: {
    requisitionForm,
    passwordReset
  }
}
</script>

<style scoped>
.navbar-header {
  height: 60px;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 1002;
}
.navbar-dark, .navbar-header .navbar-collapse {
  background-color: rgb(9, 168, 197);
  color: #fff;
}
.navbar-brand, .title {
  font-size: 20px;
}
.navbar-text a {
  text-decoration: none;
}
#navItem {
  border-left: 1px solid #fff;
  width: 33.33%
}
.modal .new-requisition {
  background-color: #f8f8f8;
}
/*@media (max-height: 768px){
  .navbar-header .navbar-nav {
    display: flex;
    flex-direction: column;
  }
}*/
</style>
