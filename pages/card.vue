<template>

  <section id="team">
    <v-main class="container">
      <h1 class="section-title">our team</h1>
      <v-row>

        <!-- Team member -->
        <v-col :class="`d-flex justify-center`" v-for="(front, index) in frontSide" :key="index">
          <div class="image-flip">
            <div class="mainflip flip-0">

              <div class="frontside">
                <v-card class="card-body text-center">
                  <img class="img-fluid" :src="front.img" alt="card image">
                  <v-card-title class="green--text justify-center">{{ cardTitle }}</v-card-title>
                  <v-card-text class="black--text">{{ cardTextFront }}</v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn text href="https://www.fiverr.com/share/qb8D02" class="frontbtn"><i
                      class="fa fa-plus"></i></v-btn>
                    <v-spacer></v-spacer>
                  </v-card-actions>
                </v-card>
              </div>

              <div class="backside">
                <v-card class="card-body text-center">
                  <v-card-title class="green--text justify-center back">{{ cardTitle }}</v-card-title>
                  <v-card-text class="black--text">{{ cardTextBack }}</v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn text class="btn-primary btn-ms" v-for="social in socialLinks" target="_blank"
                           href="https://www.fiverr.com/share/qb8D02"><i :class="social"></i></v-btn>
                    <v-spacer></v-spacer>
                  </v-card-actions>
                </v-card>
              </div>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-main>
  </section>

</template>

<script>

    export default {
        data: () => ({
            cardTitle: 'Sunlimetech',
            cardTextFront: 'This is basic card with image on top, title, description and button.',
            cardTextBack: 'This is basic card with image on top, title, description and button.This is basic card with image on top, title, description and button.This is basic card with image on top, title, description and button.',
            socialLinks: ['fa fa-facebook', 'fa fa-twitter', 'fa fa-skype', 'fa fa-google'],
            frontSide: [
                {img: 'https://sunlimetech.com/portfolio/boot4menu/assets/imgs/team/img_01.png'},
                {img: 'https://sunlimetech.com/portfolio/boot4menu/assets/imgs/team/img_02.png'},
                {img: 'https://sunlimetech.com/portfolio/boot4menu/assets/imgs/team/img_03.png'},
                {img: 'https://sunlimetech.com/portfolio/boot4menu/assets/imgs/team/img_04.jpg'},
                {img: 'https://sunlimetech.com/portfolio/boot4menu/assets/imgs/team/img_05.png'},
                {img: 'https://sunlimetech.com/portfolio/boot4menu/assets/imgs/team/img_06.jpg'}
            ],
        })
    }

</script>

<style scoped>

  @import url('https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css');

  .back {
    padding-top: 40px;
  }

  .card-body {
    background-color: #eeeeee;
    height: 310px;
    width: 400px;
    padding-left: 20px;
    padding-right: 20px;
    padding-top: 20px;
  }

  #team {
    background: lightgrey !important;
    padding-left: 210px;
    padding-right: 210px;
  }

  .frontbtn {
    color: #eeeeee;
    background-color: dodgerblue;
  }

  .btn-primary {
    color: green;
  }

  section {
    background-color: #eeeeee;
    padding: 60px 0;
  }

  section .section-title {
    text-align: center;
    color: green;
    margin-bottom: 50px;
    text-transform: uppercase;
  }

  #team {
    border: none;
    background: #eeeeee;
  }

  .image-flip:hover .backside,
  .image-flip.hover .backside {
    -webkit-transform: rotateY(0deg);
    -moz-transform: rotateY(0deg);
    -o-transform: rotateY(0deg);
    -ms-transform: rotateY(0deg);
    transform: rotateY(0deg);
    border-radius: .25rem;
  }

  .image-flip:hover .frontside,
  .image-flip.hover .frontside {
    -webkit-transform: rotateY(180deg);
    -moz-transform: rotateY(180deg);
    -o-transform: rotateY(180deg);
    transform: rotateY(180deg);
  }

  .mainflip {
    -webkit-transition: 1s;
    -webkit-transform-style: preserve-3d;
    -ms-transition: 1s;
    -moz-transition: 1s;
    -moz-transform: perspective(1000px);
    -moz-transform-style: preserve-3d;
    -ms-transform-style: preserve-3d;
    transition: 1s;
    transform-style: preserve-3d;
    position: relative;
  }

  .frontside {
    position: relative;
    -webkit-transform: rotateY(0deg);
    -ms-transform: rotateY(0deg);
    z-index: 2;
    margin-bottom: 30px;
  }

  .backside {
    position: absolute;
    top: 0;
    left: 0;
    background: #eeeeee;
    -webkit-transform: rotateY(-180deg);
    -moz-transform: rotateY(-180deg);
    -o-transform: rotateY(-180deg);
    -ms-transform: rotateY(-180deg);
    transform: rotateY(-180deg);
    -webkit-box-shadow: 5px 7px 9px -4px rgb(158, 158, 158);
    -moz-box-shadow: 5px 7px 9px -4px rgb(158, 158, 158);
    box-shadow: 5px 7px 9px -4px rgb(158, 158, 158);
  }

  .frontside,
  .backside {
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    -ms-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-transition: 1s;
    -webkit-transform-style: preserve-3d;
    -moz-transition: 1s;
    -moz-transform-style: preserve-3d;
    -o-transition: 1s;
    -o-transform-style: preserve-3d;
    -ms-transition: 1s;
    -ms-transform-style: preserve-3d;
    transition: 1s;
    transform-style: preserve-3d;
  }

  .frontside v-card,
  .backside v-card {
    min-height: 312px;
  }

  .backside a {
    font-size: 18px;
    color: #007b5e !important;
  }

  img {
    width: 120px;
    height: 120px;
    border-radius: 50%;
  }

</style>
