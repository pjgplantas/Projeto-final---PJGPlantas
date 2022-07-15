<template>
  <section>
    <div>
      <b-carousel
        id="carousel-1"
        v-model="slide"
        :interval="4000"
        background=""
        style="text-shadow: 1px 1px 2px #333"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
        fade
      >
        <b-carousel-slide
          id="c1"
          img-src="https://img.freepik.com/fotos-gratis/fundo-de-folhas-verdes-tropicais_53876-88891.jpg?t=st=1655655273~exp=1655655873~hmac=130a104d203ac8ab45624aaaa9f7d5fb5dea77ef494644a3636d38a0f738fc3a&w=1380"
        >
        </b-carousel-slide>
        <b-carousel-slide
          id="c2"
          img-src="https://img.freepik.com/fotos-gratis/foto-detalhada-de-uma-bela-folha-de-samambaia-iluminada-por-raios-de-sol-raios-de-sol-de-primavera-brilham-atraves-das-folhas-verdes-de-samambaias-nas-profundezas-de-uma-pitoresca-floresta-de-pinheiros-nas-montanhas_661209-107.jpg?t=st=1655656374~exp=1655656974~hmac=1dfe80525fb4a93927ca945d17d6590923c797d847a3623393ae8bdb99fc28d1&w=1380"
        >
        </b-carousel-slide>
      </b-carousel>
    </div>
    <div class="titlepl">PLANTAS DE AMBIENTES EXTERNOS</div>
    <b-container class="bv-example-row">
      <b-row>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_963647-MLB48382302651_112021-W.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" scale="1" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Areca Bambu</div>
            <b-card-text class="textop"> R$42,00 à vista. </b-card-text>
            <b-button class="btn1" href="/produto" variant="primary"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_962052-MLB40777905968_022020-O.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Antúrio</div>
            <b-card-text class="textop"> R$47,00 à vista. </b-card-text>
            <b-button class="btn1" href="/produto" variant="primary"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_620228-MLB49923915132_052022-W.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Moreia</div>
            <b-card-text class="textop"> R$37,00 à vista. </b-card-text>
            <b-button class="btn1" href="/produto" variant="primary"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_696917-MLB47044038890_082021-W.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Pata de Elefante</div>
            <b-card-text class="textop"> R$75,00 à vista. </b-card-text>
            <b-button class="btn1" href="/produto" variant="primary"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
      </b-row>
    </b-container>
    <div class="titlepl2">PLANTAS DE SOMBRA</div>
    <b-container class="bv-example-row" id="container2">
      <b-row>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_932966-MLB40273874684_122019-O.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Espada de São Jorge</div>
            <b-card-text class="textop"> R$45,00 à vista. </b-card-text>
            <b-button class="btn1" href="/produto" variant="primary"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_932966-MLB40273874684_122019-O.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Espada de São Jorge</div>
            <b-card-text class="textop"> R$45,00 à vista. </b-card-text>
            <b-button class="btn1" href="/produto" variant="primary"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_608050-MLB47534634700_092021-O.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Palmeira-ráfis</div>
            <b-card-text class="textop"> R$75,00 à vista. </b-card-text>
            <b-button
              class="btn1"
              href="/produto"
              variant="primary"
              style="white-space: nowrap"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
        <b-col>
          <b-card
            img-src="https://http2.mlstatic.com/D_NQ_NP_712354-MLB49960313129_052022-O.webp"
            img-alt="Image"
            img-top
            tag="article"
            style="height: 550px"
            class="titlep mb-2"
          >
            <b-icon icon="heart" variant="danger"></b-icon>
            <hr class="hrH" />
            <div class="titulo5">Pacová</div>
            <b-card-text class="textop"> R$30,00 à vista. </b-card-text>
            <b-button class="btn1" href="/produto" variant="primary"
              >Adicionar ao Carrinho</b-button
            >
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>
<script>
export default {
  data() {
    return {};
  },
};
</script>

<style>
a.btn.btn1.btn-primary {
  background: #00bf8f;  /* fallback for old browsers */
background: -webkit-(to top, #001510, #00bf8f);  /* Chrome 10-25, Safari 5.1-6 */
background: #00bf8f; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  border-radius: 5px;
  border: 0;
  padding: 10px;
  font-size: 17px;
  margin: 5% 0 0 10%;
  font-family: "Roboto", sans-serif;
  font-weight: 500;
}
a.btn.btn1.btn-primary:hover {
  background: rgba(50, 128, 81, 0.63);
}

.imgpr {
  width: 100%;
}
.card-img-top {
  height: 300px;
  border-radius: 3px;
}
.titlep {
  text-align: left;
  box-shadow: 5px 5px 8px 2px rgba(62, 150, 97, 0.95);
  border-radius: 5px;
}
.card-text {
  font-family: "Jomolhari", serif;
  font-size: 22px;
}
.titlepl {
  margin: 5% 0 0 20%;
  font-size: 29px;
  color: #099d78;
  padding: 30px;
  font-style: normal;
  font-weight: 400;
}

.titlepl2 {
  margin: 5% 0 0 21%;
  font-size: 29px;
  color: #099d78;
  font-style: normal;
  font-weight: 400;
}
.titulo5 {
  color:  #00bf8f;  /* fallback for old browsers */
color: -webkit-(to top, #001510, #00bf8f);  /* Chrome 10-25, Safari 5.1-6 */
color:  #00bf8f; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  opacity: 63%;
  font-family: "Josefin Sans", sans-serif;
  text-align: left;
  font-size: 21px;
  font-weight: bold;
  white-space: nowrap;
}
.hrH {
  border-color: black;
}
.textop {
  margin: 3% 0 3% 0;
  text-align: left;
}
#c1 {
  height: 620px;
}
#c2 {
  height: 620px;
}
@media (max-width: 844px) {
  .dprincipal {
    width: auto;
    height: auto;
  }
  .row {
    margin: 0;
  }
  .navpr {
    box-shadow: none;
  }

  .navbar-nav {
    margin-right: 100px;
  }
  #c1 {
    height: 280px;
  }
  #c2 {
    height: 280px;
  }
  .section {
    margin: 0 0 30% 0;
  }
  #footer {
    margin: 0 0 0 5%;
    display: flex;
  }
  .titlepl {
    font-size: 25px;
    text-align: left;
    margin: 0 0 5% 5%;
    padding: 10px;
  }
  .titlepl2 {
    white-space: nowrap;
    font-size: 25px;
    text-align: left;
    margin: 10% 0 5% 6%;
    padding: 10px;
  }
  .col {
    padding: 20px;
    margin: 0 20% 0 0;
  }
  .card {
    margin-left: 50px;
    width: 270px;
  }
}
</style>
