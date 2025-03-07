<template>
  <div id="main_container">
    <nav class="navbar navbar-expand-lg fixed-top">
      <div class="container">
        <a
          @click.prevent="scrollTo('#home')"
          class="navbar-brand pointer"
        >
          <img src="~/assets/logo_ru.svg" height="50" class="d-inline-block align-top" v-if="$i18n.locale == 'ru'">
          <img src="~/assets/logo_en.svg" height="50" class="d-inline-block align-top" v-if="$i18n.locale == 'en'">
        </a>
        <div class="collapse navbar-collapse">
          <div class="ml-auto">
            <ul class="navbar-nav">
              <li class="nav-item">
                <a
                  @click="scrollTo('#product')"
                  class="nav-link"
                >
                  {{ $t('products') }}
                </a>
              </li>
              <li class="nav-item">
                <a
                  @click="scrollTo('#about')"
                  class="nav-link"
                >
                  {{ $t('about') }}
                </a>
              </li>
              <li class="nav-item">
                <a
                  @click="scrollTo('#contact')"
                  class="nav-link"
                >
                  {{ $t('contacts') }}
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div class="ml-5 fs-24">
          <nuxt-link :to="switchLocalePath('ru')" class="mr-2 lang-select">🇷🇺</nuxt-link>
          <nuxt-link :to="switchLocalePath('en')" class="lang-select">🇺🇸</nuxt-link>
        </div>
      </div>
    </nav>
    <div class="page header anchor" id="home">
      <div class="container min-vh-100 d-flex flex-column align-items-center justify-content-center">
        <h1 class="title mt-auto" data-aos="fade-up" data-aos-once="true">{{ $t('title_h1') }}</h1>
        <span class="subtitle" data-aos="fade-up" data-aos-once="true">
          {{ $t('subtitle') }}
        </span>
        <a
          @click="scrollTo('#product')"
          class="btn about mt-auto mb-5"
          data-aos="fade-up"
          data-aos-anchor=".subtitle"
          data-aos-once="true"
        >
          {{ $t('more') }}
        </a>
      </div>
    </div>
    <div class="page anchor" id="product">
      <div class="container">
        <div class="row min-vh-100">
          <div
            class="col-sm-5 d-flex align-items-center mt-3"
          >
            <img
              height="auto"
              width="100%"
              src="/LandPack_Cam_03_v3_1.webp"
              data-aos="fade-up"
              data-aos-once="true"
              data-aos-offset="100"
            >
          </div>
          <div
            class="col-sm-7 d-flex flex-column justify-content-center"
            data-aos="zoom-in"
            data-aos-once="true"
            data-aos-offset="300"
          >
            <div class="mt-5">
              <h1>{{ $t('we_produce_h1') }}</h1>
              <div class="text-white mb-5 fs-24">
                {{ $t('we_produce') }}
              </div>
            </div>
            <div class="d-flex d-md-block mb-5">
              <div class="m-auto m-md-0">
                <a
                  @click="scrollTo('#contact')"
                  class="btn call-us"
                >
                  {{ $t('contact_us') }}
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="page video">
      <div class="container">
        <div class="row min-vh-100 pt-4">
          <div
            class="col d-flex flex-column justify-content-center"
            data-aos="zoom-in"
            data-aos-once="true"
          >
            <div>
              <h1>{{ $t('individual_approach_h1') }}</h1>
              <div class="text-white mb-2 mb-sm-5 fs-24">
                {{ $t('individual_approach') }}
              </div>
            </div>

            <div class="d-none d-sm-block">
              <div class="m-auto m-md-0">
                <a
                  @click="scrollTo('#contact')"
                  class="btn"
                >
                  {{ $t('order') }}
                </a>
              </div>
            </div>
          </div>
          <div class="col d-flex flex-column justify-content-center my-5">
            <div class="d-flex">
              <video
                width="90%"
                height="100%"
                playsinline
                autoplay
                muted
                loop
                class="m-auto"
                ref="theVideo"
                poster="/video_preview.webp"
              >
                <source src="/video_bg.webm" type="video/webm">
              </video>
            </div>
            <div class="d-flex mt-5 d-sm-none">
              <div class="m-auto m-md-0">
                <a
                  @click="scrollTo('#contact')"
                  class="btn"
                >
                  {{ $t('order') }}
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="product_quality anchor" id="about">
      <div
        class="py-4 product_quality_image"
      >
        <div
          class="d-flex ml-2 ml-sm-0"
          data-aos="zoom-in"
          data-aos-once="true"
        >
          <div class="m-auto d-flex flex-column text-center">
            <h1>{{ $t('product_quality_h1') }}</h1>
            <div class="text-white mx-5 fs-24" style="max-width: 600px">
              {{ $t('product_quality') }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="page lab-delivery">
      <div class="container">
        <div
          class="row min-vh-100"
          data-aos="zoom-in"
          data-aos-once="true"
        >
          <div class="col-sm-6 d-none d-sm-block" />
          <div class="col-sm-6 d-flex flex-column justify-content-center">
            <div>
              <h1>{{ $t('laboratory_h1') }}</h1>
              <div class="text-white text-sm-left text-center mb-5 fs-24">
                {{ $t('laboratory') }}
              </div>
            </div>
            <div>
              <h1>{{ $t('delivery_h1') }}</h1>
              <div class="text-white text-sm-left text-center mb-5 fs-24">
                {{ $t('delivery') }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="page d-flex flex-column min-vh-100 anchor pt-5" id="contact">
      <div class="container mt-auto " data-aos="fade-down" data-aos-once="true">
        <div class="d-flex flex-column align-content-center">
          <div class="text-center">
            <h1>
              {{ $t('contacts_h1') }}
            </h1>
          </div>
          <div class="text-center text-24">
            {{ $t('contacts_address') }}<br>
            {{ $t('contacts_phones') }}<br>
            {{ $t('contacts_email') }}
          </div>
        </div>
      </div>
      <div
        class="container text-center mt-auto"
      >
        <img width="100%" src="../assets/footer.webp">
      </div>
    </div>

    <div
      class="scroll-top"
      data-aos="fade-up"
      data-aos-anchor="#product"
    >
      <a @click="scrollTop" class="pointer">
        <img src="~/assets/scroll_top.svg">
      </a>
    </div>
  </div>
</template>

<script>
import AOS from 'aos'
import 'aos/dist/aos.css'

export default {
  head () {
    return {
      title: this.$t('seo.head_title'),
      meta: [
        { hid: 'description', name: 'description', content: this.$t('seo.description') },
        { hid: 'og:title', property: 'og:title', content: this.$t('seo.head_title') },
        { hid: 'og:url', property: 'og:url', content: this.$t('seo.url') },
        { hid: 'twitter:title', property: 'twitter:title', content: this.$t('seo.head_title') },
        { hid: 'og:description', property: 'og:description', content: this.$t('seo.description') },
        { hid: 'twitter:description', property: 'twitter:description', content: this.$t('seo.description') }
      ]
    }
  },
  mounted () {
    AOS.init({
      disabled: 'phone',
      // offset: 120,
      // delay: 200,
      duration: 1000
    })
  },
  methods: {
    scrollTop () {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    },
    scrollTo (toHash) {
      if (toHash) {
        const el = document.querySelector(toHash)
        if ('scrollBehavior' in document.documentElement.style) {
          window.scrollTo({ top: el.offsetTop, behavior: 'smooth' })
        } else {
          return window.scrollTo(0, el.offsetTop)
        }
      }
    }
  }
}
</script>
