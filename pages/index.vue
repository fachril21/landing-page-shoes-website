<template>
  <div>
    <div class="desktop hidden-sm-and-down">
      <div class="first-page">
        <div class="header container hidden-sm-and-down">
          <v-row>
            <v-col class="menu">
              <a href="#" class="d-inline menu-item">Home</a>
              <a
                href="#"
                @click="goto('katalog-desktop')"
                class="d-inline menu-item"
                >Katalog</a
              >
              <a
                href="#"
                @click="goto('about-desktop')"
                class="d-inline menu-item"
                >Tentang Kami</a
              >
              <a
                href="#"
                @click="goto('kontak-desktop')"
                class="d-inline menu-item"
                >Kontak</a
              >
            </v-col>
          </v-row>
        </div>
        <div class="container title-content">
          <v-row>
            <v-col cols="6">
              <h1 class="tagline">Pilih sepatu terbaikmu disini</h1>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="6">
              <p class="subtagline">
                Tetap dapatkan informasi tentang Produk Terbaru dan Pembelian
                Teratas. Berlangganan informasi hari ini dan dapatkan Diskon 20%
                pada pembelian berikutnya.
              </p>
            </v-col>
          </v-row>
        </div>
      </div>
      <div class="second-page" ref="katalog-desktop">
        <h2 class="text-background">
          New Arrivals
        </h2>

        <v-row align="center" justify="center" class="second-page-title">
          <h2 data-aos="fade-up" data-aos-easing="ease">New Arrivals</h2>
        </v-row>
        <v-slide-group
          id="katalog-slide"
          class="pa-4 mt-4"
          active-class="success"
          show-arrows
        >
          <v-slide-item v-for="item in items" :key="item.id">
            <v-card class="ma-4 card-outter" width="236" elevation="8">
              <template slot="progress">
                <v-progress-linear
                  color="deep-purple"
                  height="10"
                  indeterminate
                ></v-progress-linear>
              </template>

              <v-img height="250" :src="item.imgUrl"></v-img>

              <v-card-title class="card-title">{{ item.name }}</v-card-title>

              <v-card-text>
                <div class="card-price">
                  {{ item.price }}
                </div>
              </v-card-text>
            </v-card>
          </v-slide-item>
        </v-slide-group>
      </div>
      <div class="third-page" ref="about-desktop">
        <v-row align="center" justify="center">
          <v-col
            data-aos="fade-up"
            data-aos-easing="ease"
            class="content-about"
          >
            <v-row>
              <h2>Tentang Kami</h2>
            </v-row>
            <v-row style="margin-top: 24px;">
              <p class="paragraph">
                Kami merupakan reseller sepatu original dengan banyak merk
                ternama. Sepatu yang kami jual terjamin kualitasnya dengan harga
                yang bersaing. <b>Lebih dari 5000 customer</b> yang telah
                mempercayakan pilihan sepatu mereka kepada kami kami.
              </p>
            </v-row>
            <v-row style="margin-top: 48px;">
              <v-carousel
                height="256"
                hide-delimiter-background
                show-arrows-on-hover
                cycle
              >
                <v-carousel-item
                  v-for="testimoni in testimonis"
                  :key="testimoni.id"
                >
                  <v-sheet color="white" height="100%" tile>
                    <v-row class="fill-height" align="center" justify="center">
                      <div style="color: #272727" class="testimoni">
                        <v-row justify="center" style="margin-bottom: 8px;">
                          <v-avatar>
                            <img
                              :src="testimoni.avatarUrl"
                              :alt="testimoni.name"
                            />
                          </v-avatar>
                        </v-row>
                        <v-row justify="center" style="margin-bottom: 8px;">
                          <h3>{{ testimoni.name }}</h3>
                        </v-row>
                        <v-row justify="center" class="testimoni-content">
                          <p>"{{ testimoni.content }}"</p>
                        </v-row>
                      </div>
                    </v-row>
                  </v-sheet>
                </v-carousel-item>
              </v-carousel>
            </v-row>
          </v-col>
          <v-col class="collage-image">
            <v-img
              data-aos="fade-left"
              data-aos-easing="ease"
              data-aos-delay="250"
              class="ma-8"
              :src="'https://i.ibb.co/m9TzG2b/collage-about.png'"
            ></v-img>
          </v-col>
        </v-row>
      </div>
      <div class="fourth-page" ref="kontak-desktop">
        <v-row
          data-aos="fade-up"
          data-aos-easing="ease"
          style="padding-left: 120px; height: 100%;"
          align="center"
        >
          <v-col cols="6">
            <v-row>
              <h2>Mulai pilih sepatu impian kamu disini.</h2>
            </v-row>
            <v-row style="margin-top: 24px;">
              <p>
                Hubungi WhatsApp kami jika Anda ingin memesan atau jika Anda
                memiliki pertanyaan.
              </p>
            </v-row>
            <v-row>
              <v-btn color="#F27F0C" @click="gotoWA()" class="ma-2 white--text">
                <v-icon class="whatsapp-btn" left dark color="white">
                  mdi-whatsapp
                </v-icon>
                0822-3121-1511
              </v-btn>
            </v-row>
          </v-col>
        </v-row>
      </div>
      <v-footer padless>
        <v-row style="padding-inline: 120px; margin-top: 80px;">
          <v-col>
            <v-row style="margin-bottom: 24px;">
              <h3>Hubungi Kami</h3>
            </v-row>
            <v-row>
              <p>Jl. Somonegoro, Kabupaten Magetan, Jawa Timur, Indonesia</p>
            </v-row>
            <v-row>
              <p>yourshoes@gmail.com</p>
            </v-row>
            <v-row>
              <p>0822-3121-1511</p>
            </v-row>
          </v-col>
          <v-col>
            <v-row style="margin-bottom: 24px;">
              <h3>Ikuti Sosial Media Kami</h3>
            </v-row>
            <v-row>
              <v-col cols="1">
                <v-btn icon color="white">
                  <v-icon>mdi-facebook</v-icon>
                </v-btn>
              </v-col>
              <v-col cols="1">
                <v-btn icon color="white">
                  <v-icon>mdi-instagram</v-icon>
                </v-btn>
              </v-col>
              <v-col cols="1">
                <v-btn icon color="white">
                  <v-icon>mdi-twitter</v-icon>
                </v-btn>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-col class="text-center" cols="12">
          {{ new Date().getFullYear() }} —
          <strong>Fachril Rachma Zulfidar</strong>
        </v-col>
      </v-footer>
    </div>
    <div class="mobile hidden-md-and-up">
      <div class="first-page">
        <div class="header container">
          <v-app-bar-nav-icon
            color="#052134"
            @click.stop="drawer = !drawer"
          ></v-app-bar-nav-icon>

          <v-navigation-drawer v-model="drawer" absolute temporary>
            <v-list dense>
              <v-list-item @click="goto('home')">
                <v-list-item-content>
                  <v-list-item-title>Home</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
              <v-list-item @click="goto('katalog')">
                <v-list-item-content>
                  <v-list-item-title>Katalog</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
              <v-list-item @click="goto('about')">
                <v-list-item-content>
                  <v-list-item-title>Tentang Kami</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
              <v-list-item @click="goto('kontak')">
                <v-list-item-content>
                  <v-list-item-title>Kontak</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-navigation-drawer>
        </div>
      </div>
      <div class="title-div">
        <v-row
          data-aos="fade-up"
          data-aos-easing="ease"
          align="center"
          justify="center"
        >
          <span style="font-size: 20px;"
            ><b>Pilih sepatu terbaikmu disini</b></span
          >
          <span class="subtitle"
            >Tetap dapatkan informasi tentang Produk Terbaru dan Pembelian
            Teratas. Berlangganan informasi hari ini dan dapatkan Diskon 20%
            pada pembelian berikutnya.
          </span>
        </v-row>
      </div>
      <div class="second-page" ref="katalog">
        <h2 class="text-background">New Arrivals</h2>

        <v-row align="center" justify="center" class="second-page-title">
          <h2 data-aos="fade-up" data-aos-easing="ease">New Arrivals</h2>
        </v-row>
        <v-slide-group
          id="katalog-slide"
          class="pa-4 mt-4"
          active-class="success"
          show-arrows
        >
          <v-slide-item v-for="item in items" :key="item.id">
            <v-card class="ma-4 card-outter" width="200" elevation="8">
              <template slot="progress">
                <v-progress-linear
                  color="deep-purple"
                  height="10"
                  indeterminate
                ></v-progress-linear>
              </template>

              <v-img height="150" :src="item.imgUrl"></v-img>

              <v-card-title class="card-title">{{ item.name }}</v-card-title>

              <v-card-text>
                <div class="card-price">
                  {{ item.price }}
                </div>
              </v-card-text>
            </v-card>
          </v-slide-item>
        </v-slide-group>
      </div>
      <div class="third-page" ref="about">
        <div
          data-aos="fade-up"
          data-aos-easing="ease"
          style="padding-block: 48px; padding-inline: 48px;"
        >
          <v-row align="center" justify="center">
            <span><b>Tentang Kami</b></span>
            <span style="text-align: justify;">
              Kami merupakan reseller sepatu original dengan banyak merk
              ternama. Sepatu yang kami jual terjamin kualitasnya dengan harga
              yang bersaing. <b>Lebih dari 5000 customer</b> yang telah
              mempercayakan pilihan sepatu mereka kepada kami kami.
            </span>
          </v-row>
          <v-row style="margin-top: 48px;">
            <v-carousel
              height="256"
              hide-delimiter-background
              show-arrows-on-hover
              cycle
            >
              <v-carousel-item
                v-for="testimoni in testimonis"
                :key="testimoni.id"
              >
                <v-sheet color="white" height="100%" tile>
                  <v-row class="fill-height" align="center" justify="center">
                    <div style="color: #272727" class="testimoni">
                      <v-row justify="center" style="margin-bottom: 8px;">
                        <v-avatar>
                          <img
                            :src="testimoni.avatarUrl"
                            :alt="testimoni.name"
                          />
                        </v-avatar>
                      </v-row>
                      <v-row justify="center" style="margin-bottom: 8px;">
                        <h3>{{ testimoni.name }}</h3>
                      </v-row>
                      <v-row justify="center" class="testimoni-content">
                        <p>"{{ testimoni.content }}"</p>
                      </v-row>
                    </div>
                  </v-row>
                </v-sheet>
              </v-carousel-item>
            </v-carousel>
          </v-row>
          <v-row align="center" justify="center">
            <v-img :src="'https://i.ibb.co/m9TzG2b/collage-about.png'"></v-img>
          </v-row>
        </div>
      </div>
      <div class="fourth-page" ref="kontak">
        <div data-aos="fade-up" data-aos-easing="ease">
          <v-row>
            <h3>Mulai pilih sepatu impian kamu disini.</h3>
          </v-row>
          <v-row style="margin-top: 24px;">
            <p>
              Hubungi WhatsApp kami jika Anda ingin memesan atau jika Anda
              memiliki pertanyaan.
            </p>
          </v-row>
          <v-row>
            <v-btn color="#F27F0C" @click="gotoWA()" class="ma-2 white--text">
              <v-icon class="whatsapp-btn" left dark color="white">
                mdi-whatsapp
              </v-icon>
              0822-3121-1511
            </v-btn>
          </v-row>
        </div>
      </div>
      <v-footer padless>
        <v-row style="padding-inline: 48px; margin-top: 80px;">
          <v-col>
            <v-row style="margin-bottom: 16px;">
              <h3>Hubungi Kami</h3>
            </v-row>
            <v-row>
              <p>Jl. Somonegoro, Kabupaten Magetan, Jawa Timur, Indonesia</p>
            </v-row>
            <v-row>
              <p>yourshoes@gmail.com</p>
            </v-row>
            <v-row>
              <p>0822-3121-1511</p>
            </v-row>
          </v-col>
        </v-row>
        <v-row style="padding-inline: 48px; margin-top: 80px;">
          <v-col>
            <v-row style="margin-bottom: 16px;">
              <h3>Ikuti Sosial Media Kami</h3>
            </v-row>
            <v-row>
              <v-col cols="3">
                <v-btn icon color="white">
                  <v-icon>mdi-facebook</v-icon>
                </v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn icon color="white">
                  <v-icon>mdi-instagram</v-icon>
                </v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn icon color="white">
                  <v-icon>mdi-twitter</v-icon>
                </v-btn>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-col class="text-center" cols="12" style="margin-top: 48px;">
          {{ new Date().getFullYear() }} —
          <strong>Fachril Rachma Zulfidar</strong>
        </v-col>
      </v-footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: null,
      testimonis: [
        {
          id: 0,
          name: "Zach Reimund",
          avatarUrl:
            "https://i.ibb.co/HhsfN5S/pexels-elle-hughes-1680172-min.jpg",
          content:
            "Pengiriman sangat cepat, packaging rapi, sepatu sesuai pesanan. Pelayanan paling ramah."
        },
        {
          id: 1,
          name: "Alex Karev",
          avatarUrl: "https://i.ibb.co/C9R9F3g/pexels-pixabay-220453-min.jpg",
          content:
            "Pelayanan sangat ramah, barang berkualitas. Barang sampai rumah tepat waktu."
        },
        {
          id: 2,
          name: "Owen Hunt",
          avatarUrl:
            "https://i.ibb.co/k2ssrV5/pexels-italo-melo-2379004-min.jpg",
          content:
            "Banyak pilihan sepatu terbaru. Pelayanan sangat ramah. Pengiriman cepat."
        }
      ],
      items: [
        {
          id: 1,
          name: "Nike Air Max Genome",
          imgUrl: "https://i.ibb.co/SmGXhng/air-max-genome.jpg",
          price: "Rp. 2.569.000"
        },
        {
          id: 2,
          name: "Nike Air Max Pre-Day",
          imgUrl: "https://i.ibb.co/XCc4MPr/air-max-pre-day.jpg",
          price: "Rp. 1.979.000"
        },
        {
          id: 3,
          name: "LeBron 18 Low x Mimi Plange 'Higher Learning'",
          imgUrl: "https://i.ibb.co/TccQ4Zz/lebron-18-low.jpg",
          price: "Rp. 1.188.000"
        },
        {
          id: 4,
          name: "Nike Air Max 2X",
          imgUrl: "https://i.ibb.co/mRpr215/air-max-2x.jpg",
          price: "Rp. 1.279.000"
        },
        {
          id: 5,
          name: "LeBron 18 'Best 1–9'",
          imgUrl: "https://i.ibb.co/Myz7mSV/lebron-18-best-1-9.jpg",
          price: "Rp. 3.669.000"
        },
        {
          id: 6,
          name: "Ultraboost 21",
          imgUrl: "https://i.ibb.co/q1VzKnM/ultraboost-21.webp",
          price: "Rp. 2.800.000"
        },
        {
          id: 7,
          name: "Ultraboost 4.0",
          imgUrl: "https://i.ibb.co/J3NQY94/ultrabost-4-0.webp",
          price: "Rp. 2.800.000"
        },
        {
          id: 8,
          name: "SL20 Summer",
          imgUrl: "https://i.ibb.co/hWNS5Fp/SL20-Summer.webp",
          price: "Rp. 1.800.000"
        },
        {
          id: 9,
          name: "X9000L4 Heat",
          imgUrl: "https://i.ibb.co/L6LynPZ/X9000-L4-HEAT.webp",
          price: "Rp. 2.200.000"
        },
        {
          id: 10,
          name: "Ultraboost 5.0 DNA",
          imgUrl: "https://i.ibb.co/0yVYC28/ultraboost-5-0-dna.webp",
          price: "Rp. 2.800.000"
        }
      ]
    };
  },
  mounted() {},
  methods: {
    goto(refName) {
      setTimeout(() => {
        this.drawer = false;
        var element = this.$refs[refName];
        console.log(element);
        var top = element.offsetTop;
        window.scrollTo(0, top);
      }, 100);
    },
    gotoWA() {
      window.open(
        "https://wa.me/6282231211577?text=Saya%20ingin%20membeli%20sepatu",
        "_blank"
      );
    }
  }
};
</script>

<style>
@import "~/node_modules/aos/dist/aos.css";

.v-application {
  font-family: "Poppins", sans-serif;
}
@media (max-width: 959px) {
  .first-page {
    background: url("~assets/banner-sm.jpg");
    background-repeat: no-repeat;
    background-size: 100vw 100%;
    background-color: aliceblue;
    height: 480px;
  }

  .second-page {
    color: #272727;
    background-color: #d4d8e3;
  }

  .third-page {
    color: #272727;
    background-color: #ffffff;
  }

  .fourth-page {
    height: 240px;
    padding-block: 48px;
    padding-inline: 48px;
    background: url("~assets/contact-bg-sm.png");
    background-repeat: no-repeat;
    background-size: 100vw 100%;
  }

  .testimoni-content {
    font-size: 12px;
    padding-inline: 24px;
  }
}

@media (min-width: 960px) {
  .first-page {
    background: url("~assets/banner.png");
    background-repeat: no-repeat;
    background-size: 100vw 100%;
    background-color: aliceblue;
    height: 720px;
  }

  .second-page {
    height: 720px;
    background-color: #d4d8e3;
  }

  .second-page-title {
    padding-top: 48px;
    color: #272727;
  }

  .third-page {
    height: 720px;
    background-color: #ffffff;
    color: #272727;
  }

  .fourth-page {
    background: url("~assets/contact-bg.png");
    background-repeat: no-repeat;
    background-size: 100vw 100%;
    height: 720px;
  }
}

.fourth-page {
  height: 720px;
}

.header {
  padding-top: 24px;
  color: #052134;
}

.menu-item {
  margin-right: 56px;
  font-weight: 600;
  cursor: pointer;
}

.title-content {
  margin-top: 48px;
}

.tagline {
  font-weight: bolder !important;
  font-size: 3.052rem !important;
  line-height: 73px !important;

  color: #052134;
}

.subtagline {
  color: #052134;
}

a {
  position: relative;
  display: inline-block;
  font-weight: 600;
  color: #052134;
  overflow: hidden;

  background: linear-gradient(to right, #f27f0c, #f27f0c 50%, #052134 50%);

  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 200% 100%;
  background-position: 100%;
  transition: background-position 275ms ease;
}

a:hover {
  background-position: 0 100%;
}

.card-outter {
  position: relative;
  padding-bottom: 50px;
  border-radius: 8px;
  background-color: #ffffff !important;
}
.card-title {
  color: #272727;
  -ms-word-break: break-all;
  word-break: break-all;
  word-break: break-word;
  font-size: 16px;
}
.card-price {
  color: #272727;
}
.card-actions {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 0;
}
.detail-btn {
  width: 100%;
  border-radius: 0 0 4px 4px;
}
.detail-btn:hover {
  background-color: #429ebd !important;
  transition: all 0.5s;
  -webkit-transition: all 0.5s;
}

.text-background {
  position: absolute;
  text-align: center;
  z-index: 0;
  color: #272727;
  opacity: 0.05;
  font-size: 72px;
  left: 50%;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
}

.collage-image {
  padding: 24px;
  border: 8px;
}

.content-about {
  padding-left: 120px;
}

.paragraph {
  text-align: justify;
}

.testimoni {
  justify-content: center;
}

.testimoni-content {
  max-width: 343px;
  text-align: center;
  font-style: italic;
}

.title-div {
  padding-inline: 24px;
  padding-block: 48px;
  color: #272727;
  background-color: #d4d8e3;
}

.subtitle {
  text-align: center;
}
</style>
