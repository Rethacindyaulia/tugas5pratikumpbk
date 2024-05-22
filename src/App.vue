<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-fuschia text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          <q-avatar>
            <img src="https://pics.craiyon.com/2023-07-30/d9c585e711414e1cacf657167ff98cd8.webp">
          </q-avatar>
          Toko Kanjeng Ratu Retha
        </q-toolbar-title>

        <q-btn dense flat round icon="shopping_cart" @click="toggleRightDrawer" />
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab to="/home" label="Home" icon="home" />
      </q-tabs>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <q-list>
        <q-item-label header>Categories</q-item-label>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-avatar>
              <img
              src="https://m.media-amazon.com/images/I/61S0TC2k7qL.jpg"
              />
            </q-avatar>
          </q-item-section>
          <q-item-section>
            Cleansers
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-avatar>
              <img
              src="https://api.watsons.co.id/medias/prd-back-36500.jpg?context=bWFzdGVyfGltYWdlc3wyMzU5NHxpbWFnZS9qcGVnfGFEVTVMMmhrTmk4eE1qTXlOREF4TWpNNU1qUTNPQzlYVkVOSlJDMHpOalV3TUMxaVlXTnJMbXB3Wnd8ZGI4Mzg5ZTJmMTIzOGNlZDNmOGNiZDgyMTU3NjlkMDZjYWM3N2VkMDBlMmU1Yjk3OGZhNmQ3OGE3NDkxODNjNw"
              />
            </q-avatar>
          </q-item-section>
          <q-item-section>
            Moisturizers
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-avatar>
              <img
              src="https://images.somethinc.com/uploads/products/thumbs/800x800/SUN_PDP_UV_Watery.jpg"
              />
            </q-avatar>
          </q-item-section>
          <q-item-section>
            Sunscreens
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <q-list>
        <q-item-label header>Cart</q-item-label>
        <!-- Add cart items here -->
        <q-item>
          <q-item-section>
            Your cart is empty.
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <div class="q-pa-md">
        <q-carousel
          animated
          v-model="slide"
          navigation
          infinite
          :autoplay="autoplay"
          arrows
          transition-prev="slide-right"
          transition-next="slide-left"
          @mouseenter="autoplay = false"
          @mouseleave="autoplay = true"
        >
          <q-carousel-slide :name="1" class="carousel-slide" img-src="https://www.beautyhaul.com/assets/uploads/products/thumbs/800x800/COSRX_Low_pH_Good_Morning_Gel_Cleanser_150ml_2.jpg" />
          <q-carousel-slide :name="2" class="carousel-slide" img-src="https://id.stylekorean.com/cdn/shop/files/a_5e40f998-c39b-4246-b111-38fa10acb60a_1200x1200.png?v=1693449289" />
          <q-carousel-slide :name="3" class="carousel-slide" img-src="https://s3.bukalapak.com/bukalapak-kontenz-production/content_attachments/64848/original/Review_Avoskin_The_Great_Shield_Sunscreen,_Cocok_untuk_Kulit_Sensitif.JPG" />
          <q-carousel-slide :name="4" class="carousel-slide" img-src="https://ae01.alicdn.com/kf/Udcfd0ff8b22946aeaa0c11adb72acfc4x/1-1-Ramuan-Segar-Asal-Serum-Nacific-Buku-Terlaris-sangat-Baik-untuk-Kulit-Kering-Bergizi.jpg" />
        </q-carousel>
      </div>
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          <div>Skincare Store</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value
      },

      slide: ref(1),
      autoplay: ref(true)
    }
  }
}
</script>

<style>
.bg-fuschia {
  background-color: #FF00FF !important; /* Fuchsia */
}
</style>
