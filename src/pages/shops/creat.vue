<template>
    <div>
        <Breadcrumbs main="Shops" title="Creat New Shop"/>
        <!-- Container-fluid starts-->
        <div class="container-fluid">
            <div class="edit-profile">
              <div class="row">
                <div class="col-xl-4">
                  <div class="card">
                    <div class="card-header">
                      <h4 class="card-title mb-0">My Shop</h4>
                      <div class="card-options"><a class="card-options-collapse" href="#" data-toggle="card-collapse"><i class="fe fe-chevron-up"></i></a><a class="card-options-remove" href="#" data-toggle="card-remove"><i class="fe fe-x"></i></a></div>
                    </div>
                    <div class="card-body">
                      <form>
                        <div class="row mb-2">
                          <div class="col-auto"><img class="img-70 rounded-circle" alt="" src="../../assets/images/user/7.jpg"></div>
                          <div class="col">
                            <h3 class="mb-1">Dailli App Shop</h3>
                            <p class="mb-4">IT Company</p>
                          </div>
                        </div>
                        <div class="form-group">
                          <h6 class="form-label">Bio</h6>
                          <textarea class="form-control" rows="5">On the other hand, we denounce with righteous indignation</textarea>
                        </div>
                        <div class="form-group">
                          <label class="form-label">Shop Name</label>
                          <input class="form-control">
                        </div>
                        <div class="form-group">
                          <label class="form-label">Email-Address</label>
                          <input class="form-control" placeholder="your-email@domain.com">
                        </div>
                        <div class="form-group">
                          <label class="form-label">Website</label>
                          <input class="form-control" placeholder="http://Uplor .com">
                        </div>
                        <div class="form-footer">
                          <button class="btn btn-primary btn-block">Save</button>
                        </div>
                      </form>
                    </div>
                  </div>
                </div>
                <div class="col-xl-8">
                  <form class="card">
                    <div class="card-header">
                      <h4 class="card-title mb-0">Shop Detail</h4>
                      <div class="card-options"><a class="card-options-collapse" href="#" data-toggle="card-collapse"><i class="fe fe-chevron-up"></i></a><a class="card-options-remove" href="#" data-toggle="card-remove"><i class="fe fe-x"></i></a></div>
                    </div>
                    <div class="card-body">
                      <div class="row">
                        <div class="col-md-5">
                          <div class="form-group">
                            <label class="form-label">Company</label>
                            <input class="form-control" type="text" placeholder="Company">
                          </div>
                        </div>
                        <div class="col-sm-6 col-md-3">
                          <div class="form-group">
                            <label class="form-label">Main Category</label>
                            <input class="form-control" type="text" placeholder="Username">
                          </div>
                        </div>
                        <div class="col-sm-6 col-md-4">
                          <div class="form-group">
                            <label class="form-label">Sub Category</label>
                            <input class="form-control" type="email" placeholder="Email">
                          </div>
                        </div>
                        <!-- <div class="col-sm-6 col-md-6">
                          <div class="form-group">
                            <label class="form-label">First Name</label>
                            <input class="form-control" type="text" placeholder="Company">
                          </div>
                        </div>
                        <div class="col-sm-6 col-md-6">
                          <div class="form-group">
                            <label class="form-label">Last Name</label>
                            <input class="form-control" type="text" placeholder="Last Name">
                          </div>
                        </div> -->
                        <div class="col-md-12">
                          <div class="form-group">
                            <label class="form-label">Address</label>
                            <input class="form-control" type="text" placeholder="Home Address">
                          </div>
                        </div>
                        <div class="col-sm-6 col-md-4">
                          <div class="form-group">
                            <label class="form-label">City</label>
                            <input class="form-control" type="text" placeholder="City">
                          </div>
                        </div>
                        <!-- <div class="col-sm-6 col-md-3">
                          <div class="form-group">
                            <label class="form-label">Postal Code</label>
                            <input class="form-control" type="number" placeholder="ZIP Code">
                          </div>
                        </div> -->
                        <div class="col-md-5">
                          <div class="form-group">
                            <label class="form-label">Country</label>
                            <select class="form-control btn-square">
                              <option value="0">--Select--</option>
                              <option value="1">Jordan</option>
                              <option value="2">Saudi</option>
                              <option value="3">Iran</option>
                              <option value="4">India</option>
                            </select>
                          </div>
                        </div>
                        <div class="col-md-12">
                          <div class="form-group mb-0">
                            <label class="form-label">About Shop</label>
                            <textarea class="form-control" rows="5" placeholder="Enter About your description"></textarea>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="card-footer text-right">
                      <button class="btn btn-primary" type="submit">Create Detail</button>
                    </div>
                  </form>
                </div>
              </div>
            </div>
          </div>
        <!-- Container-fluid Ends-->
    </div>
</template>

<script>
  export default {
  };
</script>