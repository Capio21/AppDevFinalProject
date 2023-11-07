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
              <div class="container d-flex justify-content-center align-items-center" style="min-height: 100vh;">
    <!-- Section: Design Block -->
    <section class="text-center text-lg-start">
      <div class="card mb-3">
        <div class="row g-0 d-flex align-items-center">
          <div class="col-lg-4 d-none d-lg-flex">
            <img src="https://tse1.mm.bing.net/th?id=OIP.ZjUqDl7uXOFCE55kYXTQkQAAAA&pid=Api&P=0&h=220" alt="Trendy Pants and Shoes" class="w-100 rounded-t-5 rounded-tr-lg-0 rounded-bl-lg-5" style="margin-left:20px;"/>
          </div>
          <div class="col-lg-8">
            <div class="card-body py-5 px-md-5">
              <form>
                <!-- Email input -->
                <div class="form-outline mb-4">
                  <input type="email" id="form2Example1" class="form-control" />
                  <label class="form-label" for="form2Example1">Admin</label>
                </div>

                <!-- Password input -->
                <div class="form-outline mb-4">
                  <input type="password" id="form2Example2" class="form-control" />
                  <label class="form-label" for="form2Example2">Password</label>
                </div>

                <!-- 2 column grid layout for inline styling -->
                <div class="row mb-4">
                  <div class="col d-flex justify-content-center align-items-center">
                    <!-- Checkbox -->
                    <div class="form-check">
                      <input class="form-check-input" type="checkbox" value="" id="form2Example31" checked />
                      <label class="form-check-label" for="form2Example31"> Remember me </label>
                    </div>
                  </div>

                  <div class="col text-center">
                    <!-- Simple link -->
                    <a href="#!">Forgot password?</a>
                  </div>
                </div>

                <!-- Submit button -->
                <button type="button" class="btn btn-primary btn-block mb-4">Sign in</button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
<!-- Section: Design Block -->
    
</template>
<style>

@import'../assets/asset/css/nfront.css';



    .rounded-t-5 {
      border-top-left-radius: 0.1rem;
      border-top-right-radius: 0.1rem;
    }

    @media (min-width: 992px) {
      .rounded-tr-lg-0 {
        border-top-right-radius: 1234;
      }

      .rounded-bl-lg-5 {
        border-bottom-left-radius: 0.5rem;
      }
    }
  
</style>