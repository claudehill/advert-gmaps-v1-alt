<template>
      <div class="jumbotron jumbotron-feature p-4 p-md-5 text-white rounded bg-dark img-overlay">
        <div class="project-overlay overlay-teal"></div>
        <div class="col-md-8 px-0">
          <h1 class="display-4 font-italic">
            <span>
              <i class="fa fa-quote-left fa-2x"></i>
            </span> Help! ... the Directions to my Business Says "This Page Can't Load Google Maps Correctly"
          </h1>
          <p class="lead pt-4 my-3"> ... seen this error?  Continue reading.</p>
        </div>
      </div>
</template>

<script>
  export default {
    name: "JumbotronMain"
  }
</script>

<style scoped>

.jumbotron-feature {
  background-image: url('https://source.unsplash.com/1600x900/?programming,computer');
  background-size: cover;
  background-repeat: no-repeat;
}

.jumbotron {
  height: 400px !important;
}

@media (max-width: 768px) {
  .jumbotron {
     display: none;
  }
}

@media(max-width: 991px) {
  h1 {
    font-size: 2rem;
  }
  .jumbotron {
    max-height: 300px;
  }
  p.lead {
    display: none;
  }
}

</style>