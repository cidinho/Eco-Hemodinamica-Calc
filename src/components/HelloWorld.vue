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

           <v-card  class="mt-5 pt-5">
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
                </v-col>
              </v-row>
            </v-container>
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
    asc() {
      // return 0.007184*(this.peso^0.725)*(this.altura^0.425);
      return (
        0.007184 * Math.pow(this.altura, 0.725) * Math.pow(this.peso, 0.425)
      );
    },
    avsve() {
      return Math.pow(this.vsve, 2) * 0.785;
    },
  },
};
</script>
<style>
.calculado .v-input__slot,
.calculado .theme--light.v-label,
.calculado .theme--light.v-label input,
.calculado.theme--light.v-input input
{
  color: #ffffff;
}
.calculado .v-input__slot,
.calculado fieldset,
.calculado .theme--light.v-label {
  background: #3399ff;
}
.calculado .theme--light.v-label{
  padding: 3px 8px;
  border-radius: 5px;
}
</style>
