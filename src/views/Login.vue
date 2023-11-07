<template>
  <nav class="navbar navbar-dark bg-dark fixed-top">
                <div class="container-fluid">
                  <a class="navbar-brand" href="/">NWOW E-Bike</a>
                  
                  <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasDarkNavbar" aria-controls="offcanvasDarkNavbar" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                  </button>
                  <div class="offcanvas offcanvas-end text-bg-dark" tabindex="-1" id="offcanvasDarkNavbar" aria-labelledby="offcanvasDarkNavbarLabel">
                    <div class="offcanvas-header">
                      <h5 class="offcanvas-title" id="offcanvasDarkNavbarLabel">NWOW</h5>
                      <button type="button" class="btn-close btn-close-white" data-bs-dismiss="offcanvas" aria-label="Close"></button>
                    </div>
                    <div class="offcanvas-body">
                      <div class="input-group mb-3">
                        <input type="text" class="form-control" placeholder="Search..." aria-label="Search" aria-describedby="search-button">
                        <button class="btn btn-outline-secondary" type="button" id="search-button">Search</button>
                      </div>
                      <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
                        <li class="nav-item">
                          <li class="nav-item"><a class="nav-link" href="/">Home</a></li>
                          
                          <li class="nav-item"><a class="nav-link" href="/Contact">Contact</a></li>
                          
                          <li class="nav-item"><a class="nav-link" href="/Login">Sign-up</a></li>
                          
                        </li>
                        <li class="nav-item">
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
              </nav>
    <section class="h-100 gradient-form" style="background-color: #4a4949;">
  <div class="container py-5 h-100">
    <div class="row d-flex justify-content-center align-items-center h-100">
      <div class="col-xl-10">
        <div class="card rounded-3 text-black">
          <div class="row g-0">
            <div class="col-lg-6">
              <div class="card-body p-md-5 mx-md-4">

                <div class="text-center">
                 
                  <h4 class="mt-1 mb-5 pb-1">We are The NWOW Team kasi ediwow</h4>
                </div>

                <form>
                  <p>Please login to your account</p>

                  <div class="form-outline mb-4">
                    <input type="email" id="form2Example11" class="form-control"
                      placeholder="Phone number or email address" />
                    <label class="form-label" for="form2Example11">Username</label>
                  </div>

                  <div class="form-outline mb-4">
                    <input type="password" id="form2Example22" class="form-control" />
                    <label class="form-label" for="form2Example22">Password</label>
                  </div>

                  <div class="text-center pt-1 mb-5 pb-1">
                    <button class="btn btn-primary btn-block fa-lg gradient-custom-2 mb-3" type="button">Log
                      in</button> <br>
                    <a class="text-muted" href="#!">Forgot password?</a>
                  </div>

                  <div class="d-flex align-items-center justify-content-center pb-4">
                    <p class="mb-0 me-2">Don't have an account?</p>
                    <router-link to="/Signup">
                    <button type="button"  class="btn btn-outline-danger" >Create new</button>
                    </router-link>

                    
                  </div>

                </form>

              </div>
            </div>
            <div class="col-lg-6 d-flex align-items-center gradient-custom-2">
              <div class="container">
    <img :src="require('@/assets/asset/css/logo.png')" alt="Centered Logo" class="centered-image">
 </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
</template>
<style>
@import'../assets/asset/css/login.css';
@import'../assets/asset/css/nfront.css';
.container {
 position: relative;
 width: 100%;
 height: 100%;
 
}

.centered-image {
 position: absolute;
 top: 50%;
 left: 50%;
 transform: translate(-50%, -50%) ;
 width: 50%; /* You can adjust this to fit your design */
 height: auto;
 z-index: 1; /* Make sure the image is above any other elements */
 pointer-events: none; /* Allows clicking through the image */
 
}
</style>