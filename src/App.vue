<template>
  <v-app id="app">
    <v-container>
      <v-row style="margin: auto; padding-left: 1%; padding-right: 1%;">
        <v-col md="2" v-for="category in groups" :key="category">
          <v-btn 
          elevation="2"
          large>
            {{ category }}
          </v-btn>
        </v-col>
      </v-row>
      <v-row
        wrap
        no-gutters
        v-for="(row, rindex) in qelements"
        :key="rindex"
        style="min-width: 100%"
      >
        <v-col md="0.67" v-for="(col, cindex) in row" :key="cindex" class="box">
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-hover v-if="col.dibujar" v-slot="{ hover }">
                <v-card
                  dark
                  tile
                  flat
                  :color="hover ? 'orange' : '#19d29d'"
                  :elevation="hover ? 12 : 0"
                  v-bind="attrs"
                  v-on="on"
                >
                  <v-card-text>
                    <div class="el-num-atom">
                      {{ col.num_atomico }}
                    </div>
                    <div class="el-simbolo">
                      {{ col.simbolo }}
                    </div>
                    <div class="el-nombre text-no-wrap">
                      {{ col.nombre }}
                    </div>
                  </v-card-text>
                </v-card>
              </v-hover>
            </template>
            <v-card max-width="374">
              <v-card-text style="text-align: center;">
                <h1>{{ col.nombre }}</h1>
              </v-card-text>
              
              <v-img v-if="col.src"
                height="250"
                :src="require('./assets/'+col.simbolo+'.jpg')"
              >
                <v-row style="color: white; font-size: large;" class="v-card-content">
                <span style="color: white; font-size: large;">{{ col.num_atomico }}</span>
                <v-card-text>
                  Nombre Comun: {{ col.nombre }}
                </v-card-text>
                <v-card-text>
                  Serie Quimica: {{ col.nombre }}
                </v-card-text>
                <v-card-text>
                  Estado Natural: {{ col.nombre }}
                </v-card-text>
                <v-card-text>
                  Color: {{ col.nombre }}
                </v-card-text>
                <v-card-text>
                  Numero Atomico: {{ col.nombre }}
                </v-card-text>
                <v-card-text>
                  Grupo: {{ col.nombre }}
                </v-card-text>
                <v-card-text>
                  Dureza: {{ col.nombre }}
                </v-card-text>
                <v-card-text>
                  Masa Atomica: {{ col.nombre }}
                </v-card-text>
                </v-row>
                <v-row class="v-card-content">
                <span style="color: white; font-size: large;">{{ col.simbolo }}</span>
                </v-row>
              </v-img>
              <v-row>
                <v-card-text>
                  {{ col.num_atomico }} - {{ col.simbolo }} {{'./assets/'+col.simbolo + '.jpg'}}
                </v-card-text>
                <v-card-text>
                  Masa Atomica: {{ col.masa_atomica }}
                </v-card-text>
                <v-card-text>
                  Fase: {{ col.nombre }}
                </v-card-text>
              </v-row>
            </v-card>
          </v-tooltip>

          <!-- <v-card tile flat v-else>
            <v-card-text></v-card-text>
          </v-card> -->
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    qelements: [
      [
        {
          simbolo: "H",
          nombre: "Hidrogeno",
          num_atomico: 1,
          masa_atomica: 1.0,
          dibujar: true,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          simbolo: "He",
          nombre: "Helio",
          num_atomico: 2,
          masa_atomica: 4.0,
          dibujar: true,
        },
      ],
      [
        {
          simbolo: "Li",
          nombre: "Litio",
          num_atomico: 3,
          masa_atomica: 6.9,
          dibujar: true,
        },
        {
          simbolo: "Be",
          nombre: "Berilio",
          num_atomico: 4,
          masa_atomica: 9.0,
          dibujar: true,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          simbolo: "B",
          nombre: "Boro",
          num_atomico: 5,
          masa_atomica: 10.8,
          dibujar: true,
        },
        {
          simbolo: "C",
          nombre: "Carbono",
          num_atomico: 6,
          masa_atomica: 12.0,
          dibujar: true,
        },
        {
          simbolo: "N",
          nombre: "Nitrogeno",
          num_atomico: 7,
          masa_atomica: 14.0,
          dibujar: true,
        },
        {
          simbolo: "O",
          nombre: "Oxigeno",
          num_atomico: 8,
          masa_atomica: 15.9,
          dibujar: true,
        },
        {
          simbolo: "F",
          nombre: "Fluor",
          num_atomico: 9,
          masa_atomica: 19.0,
          dibujar: true,
        },
        {
          simbolo: "Ne",
          nombre: "Neon",
          num_atomico: 10,
          masa_atomica: 20.2,
          dibujar: true,
        },
      ],
      [
        {
          simbolo: "Na",
          nombre: "Sodio",
          num_atomico: 11,
          masa_atomica: 25.0,
          dibujar: true,
        },
        {
          simbolo: "Mg",
          nombre: "Magnesio",
          num_atomico: 12,
          masa_atomica: 24.3,
          dibujar: true,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          dibujar: false,
        },
        {
          simbolo: "Al",
          nombre: "Aluminio",
          num_atomico: 13,
          masa_atomica: 27.0,
          dibujar: true,
        },
        {
          simbolo: "Si",
          nombre: "Silicio",
          num_atomico: 14,
          masa_atomica: 18.1,
          dibujar: true,
        },
        {
          simbolo: "P",
          nombre: "Fosforo",
          num_atomico: 15,
          masa_atomica: 30.97,
          dibujar: true,
        },
        {
          simbolo: "S",
          nombre: "Azufre",
          num_atomico: 16,
          masa_atomica: 30.97,
          dibujar: true,
        },
        {
          simbolo: "Cl",
          nombre: "Cloro",
          num_atomico: 17,
          masa_atomica: 35.453,
          dibujar: true,
        },
        {
          simbolo: "Ar",
          nombre: "Argon",
          num_atomico: 18,
          masa_atomica: 39.948,
          dibujar: true,
        },
      ],
      [
        {
          simbolo: "K",
          nombre: "Potasio",
          num_atomico: 19,
          masa_atomica: 39.0983,
          dibujar: true,
        },
        {
          simbolo: "Ca",
          nombre: "Calcio",
          num_atomico: 20,
          masa_atomica: 40.078,
          dibujar: true,
          src: './assets/Ca.jpg'
        },
        {
          simbolo: "Sc",
          nombre: "Escandio",
          num_atomico: 21,
          masa_atomica: 44.95591,
          dibujar: true,
        },
        {
          simbolo: "Ti",
          nombre: "Titanio",
          num_atomico: 22,
          masa_atomica: 47.867,
          dibujar: true,
        },
        {
          simbolo: "V",
          nombre: "Vanadio",
          num_atomico: 23,
          masa_atomica: 50.9415,
          dibujar: true,
        },
        {
          simbolo: "Cr",
          nombre: "Cromo",
          num_atomico: 24,
          masa_atomica: 51.9962,
          dibujar: true,
        },
        {
          simbolo: "Mn",
          nombre: "Magnesio",
          num_atomico: 25,
          masa_atomica: 54.93804,
          dibujar: true,
        },
        {
          simbolo: "Fe",
          nombre: "Hierro",
          num_atomico: 26,
          masa_atomica: 55.845,
          dibujar: true,
          src: './assets/Fe.jpg'
        },
        {
          simbolo: "Co",
          nombre: "Cobalto",
          num_atomico: 27,
          masa_atomica: 58.93319,
          dibujar: true,
        },
        {
          simbolo: "Ni",
          nombre: "Niquel",
          num_atomico: 28,
          masa_atomica: 58.6934,
          dibujar: true,
        },
        {
          simbolo: "Cu",
          nombre: "Cobre",
          num_atomico: 29,
          masa_atomica: 63.546,
          dibujar: true,
          src: './assets/Cu.jpg'
        },
        {
          simbolo: "Zn",
          nombre: "Zinc",
          num_atomico: 30,
          masa_atomica: 65.38,
          dibujar: true,
        },
        {
          simbolo: "Ga",
          nombre: "Galio",
          num_atomico: 31,
          masa_atomica: 69.723,
          dibujar: true,
        },
        {
          simbolo: "Ge",
          nombre: "Germanio",
          num_atomico: 32,
          masa_atomica: 72.64,
          dibujar: true,
        },
        {
          simbolo: "As",
          nombre: "Arsenico",
          num_atomico: 33,
          masa_atomica: 74.9216,
          dibujar: true,
        },
        {
          simbolo: "Se",
          nombre: "Selenio",
          num_atomico: 34,
          masa_atomica: 78.96,
          dibujar: true,
        },
        {
          simbolo: "Br",
          nombre: "Bromio",
          num_atomico: 35,
          masa_atomica: 79.904,
          dibujar: true,
        },
        {
          simbolo: "Kr",
          nombre: "Kripton",
          num_atomico: 36,
          masa_atomica: 83.798,
          dibujar: true,
        },
      ],
      [
        {
          simbolo: "Rb",
          nombre: "Rubidio",
          num_atomico: 37,
          masa_atomica: 85.4678,
          dibujar: true,
        },
        {
          simbolo: "Sr",
          nombre: "Estronico",
          num_atomico: 38,
          masa_atomica: 87.62,
          dibujar: true,
        },
        {
          simbolo: "Y",
          nombre: "Itrio",
          num_atomico: 39,
          masa_atomica: 88.90585,
          dibujar: true,
        },
        {
          simbolo: "Zr",
          nombre: "Zirconio",
          num_atomico: 40,
          masa_atomica: 91.224,
          dibujar: true,
        },
        {
          simbolo: "Nb",
          nombre: "Niobio",
          num_atomico: 41,
          masa_atomica: 92.90638,
          dibujar: true,
        },
        {
          simbolo: "Mo",
          nombre: "Molibdeno",
          num_atomico: 42,
          masa_atomica: 95.96,
          dibujar: true,
          src: './assets/Mo.jpg'
        },
        {
          simbolo: "Tc",
          nombre: "Tecnecio",
          num_atomico: 43,
          masa_atomica: 98,
          dibujar: true,
        },
        {
          simbolo: "Ru",
          nombre: "Rutenio",
          num_atomico: 44,
          masa_atomica: 101.07,
          dibujar: true,
        },
        {
          simbolo: "Rh",
          nombre: "Rodio",
          num_atomico: 45,
          masa_atomica: 102.9055,
          dibujar: true,
        },
        {
          simbolo: "Pd",
          nombre: "Paladio",
          num_atomico: 46,
          masa_atomica: 106.42,
          dibujar: true,
        },
        {
          simbolo: "Ag",
          nombre: "Plata",
          num_atomico: 47,
          masa_atomica: 107.8682,
          dibujar: true,
          src: './assets/Ag.jpg'
        },
        {
          simbolo: "Cd",
          nombre: "Cadmio",
          num_atomico: 48,
          masa_atomica: 112.441,
          dibujar: true,
        },
        {
          simbolo: "In",
          nombre: "Indio",
          num_atomico: 49,
          masa_atomica: 114.818,
          dibujar: true,
        },
        {
          simbolo: "Sn",
          nombre: "Estano",
          num_atomico: 50,
          masa_atomica: 118.71,
          dibujar: true,
        },
        {
          simbolo: "Sb",
          nombre: "Antimonio",
          num_atomico: 51,
          masa_atomica: 121.76,
          dibujar: true,
        },
        {
          simbolo: "Te",
          nombre: "Telurio",
          num_atomico: 52,
          masa_atomica: 127.6,
          dibujar: true,
        },
        {
          simbolo: "I",
          nombre: "Yodo",
          num_atomico: 53,
          masa_atomica: 126.9044,
          dibujar: true,
        },
        {
          simbolo: "Xe",
          nombre: "Xenon",
          num_atomico: 54,
          masa_atomica: 131.293,
          dibujar: true,
        },
      ],
      [
        {
          simbolo: "Cs",
          nombre: "Cesio",
          num_atomico: 55,
          masa_atomica: 132.9054,
          dibujar: true,
        },
        {
          simbolo: "Ba",
          nombre: "Bario",
          num_atomico: 56,
          masa_atomica: 137.327,
          dibujar: true,
        },
        {
          simbolo: "Lu",
          nombre: "Lutecio",
          num_atomico: 71,
          masa_atomica: 174.9668,
          dibujar: true,
        },
        {
          simbolo: "Hf",
          nombre: "Hafnio",
          num_atomico: 72,
          masa_atomica: 178.49,
          dibujar: true,
        },
        {
          simbolo: "Ta",
          nombre: "Tantalio",
          num_atomico: 73,
          masa_atomica: 180.9478,
          dibujar: true,
        },
        {
          simbolo: "W",
          nombre: "Wolframio",
          num_atomico: 74,
          masa_atomica: 183.84,
          dibujar: true,
        },
        {
          simbolo: "Re",
          nombre: "Renio",
          num_atomico: 75,
          masa_atomica: 186.207,
          dibujar: true,
        },
        {
          simbolo: "Os",
          nombre: "Osmio",
          num_atomico: 76,
          masa_atomica: 190.23,
          dibujar: true,
        },
        {
          simbolo: "Ir",
          nombre: "Iridio",
          num_atomico: 77,
          masa_atomica: 192.217,
          dibujar: true,
        },
        {
          simbolo: "Pt",
          nombre: "Platino",
          num_atomico: 78,
          masa_atomica: 195.084,
          dibujar: true,
        },
        {
          simbolo: 'Au',
          nombre: 'Oro',
          num_atomico: 79,
          masa_atomica: 196.9665,
          dibujar: true,
          src: './assets/Au.jpg'
        },
        {
          simbolo: "Hg",
          nombre: "Mercurio",
          num_atomico: 80,
          masa_atomica: 200.59,
          dibujar: true,
        },
        {
          simbolo: "Tl",
          nombre: "Talio",
          num_atomico: 81,
          masa_atomica: 204.3833,
          dibujar: true,
        },
        {
          simbolo: "Pb",
          nombre: "Plomo",
          num_atomico: 82,
          masa_atomica: 207.2,
          dibujar: true,
        },
        {
          simbolo: "Bi",
          nombre: "Bismuto",
          num_atomico: 83,
          masa_atomica: 208.9804,
          dibujar: true,
        },
        {
          simbolo: "Po",
          nombre: "Polonio",
          num_atomico: 84,
          masa_atomica: 210,
          dibujar: true,
        },
        {
          simbolo: "At",
          nombre: "Astato",
          num_atomico: 85,
          masa_atomica: 210,
          dibujar: true,
        },
        {
          simbolo: "Rn",
          nombre: "Radon",
          num_atomico: 86,
          masa_atomica: 220,
          dibujar: true,
        },
      ],
      [
        {
          simbolo: "Fr",
          nombre: "Francio",
          num_atomico: 87,
          masa_atomica: 223,
          dibujar: true,
        },
        {
          simbolo: "Ra",
          nombre: "Radio",
          num_atomico: 88,
          masa_atomica: 226,
          dibujar: true,
        },
        {
          simbolo: "Lr",
          nombre: "Laurencio",
          num_atomico: 103,
          masa_atomica: 262,
          dibujar: true,
        },
        {
          simbolo: "Rf",
          nombre: "Rutherfordio",
          num_atomico: 104,
          masa_atomica: 261,
          dibujar: true,
        },
        {
          simbolo: "Db",
          nombre: "Dubnio",
          num_atomico: 105,
          masa_atomica: 262,
          dibujar: true,
        },
        {
          simbolo: "Sg",
          nombre: "Seaborgio",
          num_atomico: 106,
          masa_atomica: 266,
          dibujar: true,
        },
        {
          simbolo: "Bh",
          nombre: "Bohrio",
          num_atomico: 107,
          masa_atomica: 264,
          dibujar: true,
        },
        {
          simbolo: "Hs",
          nombre: "Hassio",
          num_atomico: 108,
          masa_atomica: 277,
          dibujar: true,
        },
        {
          simbolo: "Mt",
          nombre: "Meitnerio",
          num_atomico: 109,
          masa_atomica: 268,
          dibujar: true,
        },
        {
          simbolo: "Ds",
          nombre: "Darmstatio",
          num_atomico: 110,
          masa_atomica: 271,
          dibujar: true,
        },
        {
          simbolo: "Rg",
          nombre: "Roenfgenio",
          num_atomico: 111,
          masa_atomica: 272,
          dibujar: true,
        },
        {
          simbolo: "Cn",
          nombre: "Copernicio",
          num_atomico: 112,
          masa_atomica: 285,
          dibujar: true,
        },
        {
          simbolo: "Nh",
          nombre: "Nihonio",
          num_atomico: 113,
          masa_atomica: 284,
          dibujar: true,
        },
        {
          simbolo: "Fl",
          nombre: "Flerovio",
          num_atomico: 114,
          masa_atomica: 289,
          dibujar: true,
        },
        {
          simbolo: "Mc",
          nombre: "Moscovio",
          num_atomico: 115,
          masa_atomica: 288,
          dibujar: true,
        },
        {
          simbolo: "Lv",
          nombre: "Livermorio",
          num_atomico: 116,
          masa_atomica: 292,
          dibujar: true,
        },
        {
          simbolo: "Ts",
          nombre: "Teneso",
          num_atomico: 117,
          masa_atomica: 294,
          dibujar: true,
        },
        {
          simbolo: "Og",
          nombre: "Oganeson",
          num_atomico: 118,
          masa_atomica: 294,
          dibujar: true,
        },
      ],
    ],
    groups: [
      'Metales',
      'Gases',
      'Liquidos',
      'Indeterminado',
      'En Ecuador'
    ]
  }),
};
</script>

<style scoped>
.el-nombre {
  font-size: 55%;
}

.el-num-atom {
  font-size: 70%;
  text-align: center;
}

.el-simbolo {
  text-align: center;
}

.box {
  max-width: 80px;
  width: 60px;
  text-align: center;
}

.v-tooltip__content {
  font-size: 50px !important;
  background-color: white;
}

.v-card-content {
  display: flex; 
  width: 100%; 
  margin: auto; 
  align-items: center; 
  justify-content: center;
}
</style>