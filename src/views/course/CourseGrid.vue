<script setup>
import CourseBreadcrumb from "@/components/course/CourseBreadcrumb.vue";
import {ref} from "vue";
import axios from "axios";

const data = ref([])

axios.get('http://localhost:8080/system/course/list').then(res => {
  data.value = res.data.rows
})
</script>

<template>
  <div>
    <course-breadcrumb :course-count="data.length"/>
    <div class="featured-course-4-area single-page">
      <div class="container">
        <div class="row">
          <!-- Single Card -->
          <div class="col-md-6 col-lg-4" v-for="course in data">
            <div class="course-card-4-area">
              <!-- Shape -->
              <div class="care-shape-4 wow fadeInDown" data-wow-delay="700ms" style="visibility: visible; animation-delay: 700ms; animation-name: fadeInDown;">
                <img src="/img/bg-img/home-2/care-shap.png" alt="">
              </div>
              <div class="course-img-4 bg-img" style="background-image: url(/img/bg-img/home-4/shape-2.png);">
                <div class="course-sub-title">
                  <h6>主讲老师 {{ course.teacher }}</h6>
                </div>
                <div class="course-title-img">
                  <img :src="`/img/bg-img/home-4/c-${course.id}.png`" alt="">
                </div>
                <!-- Shape -->
                <div class="course-shape-4">
                  <img src="/img/bg-img/home-4/shape-3.png" alt="">
                </div>
                <div class="course-offer-4">
                  <div class="offer-bg-shape relative">
                    <img src="/img/bg-img/home-4/shape-4.png" alt="">
                  </div>
                  <div class="offer-content-4 ">
                    <p>-20%</p>
                    <span>Off</span>
                  </div>
                </div>
              </div>
              <!-- Content -->
              <div class="course-content-info-4">
                <div class="course-content-rating d-flex justify-content-between align-items-center">
                  <p><i class="icon-star1"></i> 4.5 <span>(0 Reviews)</span></p>
                  <div class="ribbon-icon">
                    <i class="icon-icon_ribbon_alt"></i>
                  </div>
                </div>
                <!-- info -->
                <div class="course-info-meta-4 d-flex align-items-center">
                  <p><i class="icon-Home"></i> 1 Student</p>
                  <p><i class="icon-book-solid-1"></i> 8 Lessone</p>
                </div>
                <h2><a href="course-details.html">{{ course.title }}</a></h2>
                <p class="course-desc-4">Podcasts like Wow in the World, Brains On!, and But Why?
                  cover
                  interesting.</p>
                <div class="auth-info-4 d-flex align-items-center">
                  <img class="auth-img" src="/img/bg-img/home-4/c-2.png" alt="">
                  <p>By <a href="#">{{ course.teacher }}</a></p>
                </div>
                <!-- Price & Cart -->
                <div class="course-footer-4 d-flex align-items-center justify-content-between">
                  <div class="course-price">
                    <p>$150 <span>$100</span></p>
                  </div>
                  <div class="course-buy">
                    <p><a href="#"><i class="icon-icon_cart_alt"></i> <span>添加到购物车</span></a>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-12">
            <div class="load-btn-area text-center mt-20">
              <a class="load-btn" href="#"><i class="icon-icon_document_alt"></i> 加载更多</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>