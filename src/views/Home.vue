<template>
  <div class="container-wrapper">
    <div class="container">
      <header class="blog-header py-3">
        <div class="row justify-content-between align-items-center">
          <div class="col-3 flex-nowrap d-flex justify-content-begin align-items-center">
            <router-link
              to="/subscribe"
              class="btn btn-outline-info btn-lg-only"
            >Subscribe to Newsletter</router-link>
          </div>

          <div class="col-6 text-center">
            <router-link class="blog-header-logo text-dark" to="/">
              A Techitorial
              <br />
              <span>by Main Avenue Design Co.</span>
            </router-link>
          </div>

          <div class="btn-lg-only col-3 d-flex justify-content-end align-items-center">
            <router-link to="/contact" class="btn btn-outline-info btn-lg-only">Contact Us</router-link>
          </div>
        </div>
      </header>

      <JumbotronMain />

      <main role="main" class="container">
        <div class="row">
          <div class="col-md-12 col-lg-8 blog-main">
            <h3 class="pb-2 mb-4 border-bottom dark-grey blog-header-font" style="font-size:2rem;" id="lead-in">
              <span class>
                <i class="fa fa-microphone teal"></i>
              </span> From our Design Team...
            </h3>

            <ContentMain />

            <div class="d-md-none col-sm-12">
              <router-link to="/contact" class="btn btn-outline-info btn-sm-only">Contact Us</router-link>
            </div>
            <div class="d-md-none col-sm-12">
              <router-link
                to="/subscribe"
                class="btn btn-outline-info btn-sm-only"
              >Subscribe to Newsletter</router-link>
            </div>
          </div>
          <Sidebar />
        </div>
        <FeaturedPost />
        <Comments />
      </main>
    </div>

    <Footer />
  </div>
</template>

<style scoped>
@import "../assets/styles/blog.css";
.blue {
  color: #3974d8;
}

.teal {
  color: #17a2b8;
}
.btn-outline-info,
#mc-embedded-subscribe {
  /* color: #3974d8;
  border-color: #3974d8; */
  color: #17a2b8;
  border-color: #17a2b8;
  border-radius: 20px;
  height: 40px;
}

.btn-outline-info:hover {
  color: #fff;
  background-color: #17a2b8;
}


.btn-round {
  width: 60px;
  height: 60px;
  border: 1px solid;
  border-radius: 50%;
}


/* Extra small devices (portrait phones, less than 576px)
No media query since this is the default in Bootstrap */

/* Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) {
}

/* Medium devices (tablets, 768px and up) */
@media (min-width: 768px) {
}
@media (max-width: 767px) {
  #lead-in {
    display:none;
  }
}

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
  .btn-lg-only {
    display: block;
  }
  .btn-sm-only {
    display: none;
  }
}

@media (max-width: 991px) {
  .blog-header-logo {
    font-size: 2rem;
  }
  .btn-lg-only {
    display: none;
  }

  h3 {
    font-size: 1.5rem !important;
  }

  .btn-sm-only {
    display: block;
    margin-top: 25px !important;
  }
  .blog-post-title {
    font-size: 1.4rem !important;
  }
}

/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {
}
</style>


<script>
// @ is an alias to /src

import ContentMain from "@/components/ContentMain.vue";
import Footer from "@/components/Footer.vue";
import JumbotronMain from "@/components/JumbotronMain.vue";
import FeaturedPost from "@/components/FeaturedPost.vue";
import MapDemo from "@/components/MapDemo.vue";
import Sidebar from "@/components/Sidebar.vue";
import Comments from "@/components/Comments.vue";

export default {
  name: "home",
  components: {
    ContentMain,
    Footer,
    Comments,
    JumbotronMain,
    FeaturedPost,
    MapDemo,
    Sidebar
  },
  created() {
    // this.$forceUpdate();
  },
  mounted() {
    this.checkAdblock();
  },
  methods: {
    checkAdblock: function() {
      setTimeout(() => {
        if (document.getElementById("369379917555767") == undefined) {
          console.log("adblock detected, redirecting in 5 seconds ...");

          // Redirect to adblock page after 5 seconds
          return setTimeout(() => {
            this.$router.push({ name: "adblock" });
          }, 5 * 1000);
        }
      }, 10 * 1000);
    }
  }
};
</script>
