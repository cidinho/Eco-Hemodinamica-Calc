<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <div class="display-1 font-weight-bold">
          AVALIAÇÃO HEMODINÂMICO PELO ECOCARDIGORAMA
        </div>
      </v-col>

      <v-col class="mb-4">
        <v-form>
          <v-card color="#ffff66" class="pt-5">
            <v-container>
              <v-row>
                <v-col cols="12" sm="12">
                  <v-text-field
                    outlined
                    v-model="peso"
                    label="Peso"
                    suffix="Kg"
                  ></v-text-field>
                  <v-text-field
                    outlined
                    v-model="altura"
                    label="Altura"
                    suffix="cm"
                  ></v-text-field>
                  <v-text-field
                    outlined
                    filled
                    v-model="asc"
                    label="ASC"
                    suffix="m²"
                    color="white"
                    class="calculado"
                  ></v-text-field>
                  <v-divider class="mb-5"></v-divider>
                  <v-text-field
                    outlined
                    v-model="fc"
                    label="FC"
                    suffix="BPM"
                  ></v-text-field>
                  <v-text-field
                    outlined
                    v-model="pam"
                    label="PAM"
                    suffix="mmHg"
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-container>
          </v-card>

          <v-card color="#FFCC00" class="mt-5 pt-5">
            <v-container>
              <v-row>
                <v-col cols="12" sm="12">
                  <v-text-field
                    outlined
                    v-model="pvce"
                    label="PVC estimada"
                    suffix="mmHg"
                  ></v-text-field>
                  <v-divider class="mb-5"></v-divider>
                  <v-text-field
                    outlined
                    v-model="vsve"
                    label="DIÂMETRO DA VSVE"
                    suffix="cm"
                  ></v-text-field>
                  <v-text-field
                    outlined
                    filled
                    v-model="avsve"
                    label="ÁREA SECCIONAL DA VSVE"
                    suffix="cm"
                    color="white"
                    class="calculado"
                  ></v-text-field>
                  <v-divider class="mb-5"></v-divider>
                  <v-text-field
                    outlined
                    v-model="vti"
                    label="VTI VSVE"
                    suffix="cm"
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-container>
          </v-card>

          <v-card class="mt-5 pt-5">
            <v-container>
              <v-row>
                <v-col cols="12" sm="12">
                  <v-text-field
                    outlined
                    filled
                    v-model="volumesve"
                    label="Volume sistólico VE"
                    suffix="ml"
                    color="white"
                    class="calculado"
                  ></v-text-field>
                  <v-text-field
                    outlined
                    filled
                    v-model="debitocardiaco"
                    label="DÉBITO CARDÍACO"
                    suffix="L/min"
                    color="white"
                    class="calculado"
                  ></v-text-field>
                  <v-text-field
                    outlined
                    filled
                    v-model="indicecardiaco"
                    label="ÍNDICE CARDÍACO"
                    suffix="L/min/m²"
                    color="white"
                    hint="2,8 – 4,2 L/min/m²"
                    persistent-hint
                    class="calculado"
                  ></v-text-field>
                  <v-text-field
                    outlined
                    filled
                    v-model="rvsp"
                    label="RVSP"
                    suffix="dinas/seg/cm-5"
                    color="white"
                    hint="900 – 1400 dinas/seg/cm-5 "
                    persistent-hint
                    class="calculado"
                  ></v-text-field>
                  <v-divider class="mb-5"></v-divider>
                  <v-text-field
                    outlined
                    filled
                    v-model="indicesistolico"
                    label="Indice do volume sistólico"
                    suffix="ml/m²"
                    color="white"
                    hint="30 – 70 ml/m²"
                    persistent-hint
                    class="calculado"
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-container>
          </v-card>

          <v-card class="mt-5 pt-5" tile>
            <v-list flat>
              <v-subheader class="display-1">Legenda</v-subheader>
              <v-list-item-group color="primary">
                <v-list-item>
                  <v-list-item-icon>
                    <v-avatar color="#ffff66" size="56"></v-avatar>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Variaveis Clínicas</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-avatar color="#FFCC00" size="56"></v-avatar>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Varáveis Ecocardigráficas</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-avatar color="#3399ff" size="56"></v-avatar>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Varáveis Calculadas</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    peso: "",
    altura: "",
    pvce: "",
    fc: "",
    pam: "",
    vsve: "",
    vti: "",
  }),
  computed: {
    C21() {
      return (this.avsve * this.vti * this.fc) / 1000;
    },
    C22() {
      return (
        (this.avsve * this.vti * this.fc) /
        1000 /
        (0.007184 * Math.pow(this.altura, 0.725) * Math.pow(this.peso, 0.425))
      );
    },
    H22() {
      return this.C22 * 1000;
    },
    asc() {
      // return 0.007184*(this.peso^0.725)*(this.altura^0.425);
      return (
        0.007184 *
        Math.pow(this.altura, 0.725) *
        Math.pow(this.peso, 0.425)
      ).toFixed(3);
    },
    avsve() {
      return Math.pow(this.vsve, 2) * 0.785;
    },
    volumesve() {
      return (this.avsve * this.vti).toFixed(2);
    },
    debitocardiaco() {
      return ((this.avsve * this.vti * this.fc) / 1000).toFixed(2);
    },
    indicecardiaco() {
      return this.asc != 0
        ? ((this.volumesve * this.fc) / 1000 / this.asc).toFixed(2)
        : 0;
    },
    rvsp() {
      return this.debitocardiaco != 0
        ? (((this.pam - this.pvce) * 80) / this.C21).toFixed(2)
        : 0;
    },
    indicesistolico() {
      return this.fc ? (this.H22 / this.fc).toFixed(2) : 0;
    },
  },
};
</script>
<style>
.calculado .v-input__slot,
.calculado .theme--light.v-label,
.calculado .theme--light.v-label input,
.calculado.theme--light.v-input input {
  color: #ffffff;
}
.calculado .v-input__slot,
.calculado fieldset,
.calculado .theme--light.v-label {
  background: #3399ff;
}
.calculado .theme--light.v-label {
  padding: 3px 8px;
  border-radius: 5px;
}
</style>
