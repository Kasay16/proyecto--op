<template>
  <v-container>
    <v-row class="mb-6" justify="center">
      <v-sheet>
        <!-- <h1>Resultado: {{ count }}</h1> -->
        <h1>Vue CandyAce</h1>
      </v-sheet>
    </v-row>
    <v-row class="mb-6" justify="center">
      <!-- Tarjeta Izquierda -->
      <v-col>
        <v-sheet :elevation="24" class="pa-2 ma-2">
          <v-container>
            <v-row justify="center">
              <v-col>
                <v-sheet>
                  <h1 class="text-primary">Resultado: {{ finalResult }}</h1>
                </v-sheet>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col>
                <v-sheet>
                  <h3 class="text-primary">Numero uno</h3>
                  <v-text-field
                    v-model="numberOne"
                    type="number"
                    :rules="rules"
                  ></v-text-field>
                </v-sheet>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col>
                <v-sheet>
                  <h3 class="text-primary">Numero dos</h3>
                  <v-text-field
                    v-model="numberTwo"
                    type="number"
                    :rules="rules"
                  ></v-text-field>
                </v-sheet>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col>
                <v-sheet class="pa-2 ma-2">
                  <v-btn class="ma-2" color="primary" @click="sumMet"
                    >Suma (+)</v-btn
                  >
                </v-sheet>
              </v-col>
              <v-col>
                <v-sheet class="pa-2 ma-2">
                  <v-btn class="ma-2" color="primary" @click="RestaMet"
                    >Resta (-)</v-btn
                  >
                </v-sheet>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col>
                <v-sheet class="pa-2 ma-2">
                  <v-btn class="ma-2" color="primary" @click="MultiMet"
                    >Multi (*)</v-btn
                  >
                </v-sheet>
              </v-col>
              <v-col>
                <v-sheet class="pa-2 ma-2">
                  <v-btn class="ma-2" color="primary" @click="DiviMet"
                    >Division (/)</v-btn
                  >
                </v-sheet>
              </v-col>
            </v-row>
          </v-container>
        </v-sheet>
      </v-col>

      <!-- Tarjeta Derecha -->
      <v-col>
        <v-sheet class="pa-2 ma-2">
          <v-row class="mb-6" justify="center">
            <v-text-field type="number" :rules="rules"></v-text-field>
          </v-row>
          <v-row class="mb-6" justify="center">
            <v-text-field type="number" :rules="rules"></v-text-field>
          </v-row>
        </v-sheet>
      </v-col>
    </v-row>

    <v-row class="mb-6" justify="center">
      <v-sheet>
        <v-btn @click="ResetInputs">Reset</v-btn>
      </v-sheet>
    </v-row>
    <v-row class="mb-6" justify="center">
      <v-sheet>
        <v-btn @click="increment">Incremetar</v-btn>
      </v-sheet>
    </v-row>
    <v-row class="mb-6" justify="center">
      <v-sheet>
        <v-btn @click="decrement">Decrementar</v-btn>
      </v-sheet>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      finalResult: 0,
      numberOne: 0,
      numberTwo: 0,
    };
  },
  // data: () => ({
  //   //Rules data input number
  //   rules: [
  //     (value) => !!value || "El campo es requerido.",
  //     (value) =>
  //       (value || "").length <= 5 ||
  //       "El campo solo puede tener un maximo de 5 caracteres",
  //     (value) => {
  //       const pattern = /^[0-9]+$/;
  //       return pattern.test(value) || "El campo solo permite numeros.";
  //     },
  //   ],
  // }),

  methods: {
    sumMet() {
      this.finalResult = parseInt(this.numberOne) + parseInt(this.numberTwo);
    },

    RestaMet() {
      this.finalResult = parseInt(this.numberOne) - parseInt(this.numberTwo);
    },

    MultiMet() {
      this.finalResult = parseInt(this.numberOne) * parseInt(this.numberTwo);
    },

    DiviMet() {
      this.finalResult = (parseInt(this.numberOne))/(parseInt(this.numberTwo));
    },

    ResetInputs() {
      this.numberOne = 0;
      this.numberTwo = 0;
      this.finalResult = 0;
    },

    increment() {
      this.count++;
    },
    decrement() {
      var valor = this.count;
      var result = valor--;
      if (result <= 0) {
        alert("El valor no puede ser menos de 0");
      } else {
        this.count--;
      }
    },
  },
};
</script>
