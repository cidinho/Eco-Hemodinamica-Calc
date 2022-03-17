<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <div class="display-1 font-weight-bold">
          Avaliação do Débito Cardíaco e Resistência Vascular Sistêmica com o
          Ecocardiograma.
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
                    hint="4 - 8 L/min"
                    persistent-hint
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
                    <v-list-item-title
                      >Varáveis Ecocardigráficas</v-list-item-title
                    >
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
          <v-card class="mt-5 pt-5" tile>
            <v-subheader class="display-1"
              >Referências e leitura recomendada</v-subheader
            >
            <p class="d-inline-block text-justify body-2 pt-3 px-3 mx-2">
              Zhang Y, Wang Y, Shi J, Hua Z, Xu J (2019) Cardiac output
              measurements via echocardiography versus thermodilution: A
              systematic review and meta-analysis. PLoS ONE 14(10): e0222105.
              <a
                target="__blank"
                href="https://doi.org/10.1371/journal.pone.0222105"
                >https://doi.org/10.1371/journal.pone.0222105</a
              >
            </p>
            <p class="d-inline-block text-justify body-2 pt-3 px-3 mx-2">
              Porter TR, Shillcutt SK, Adams MS, Desjardins G, Glas KE, Olson
              JJ, Troughton RW. Guidelines for the use of echocardiography as a
              monitor for therapeutic intervention in adults: a report from the
              American Society of Echocardiography. J Am Soc Echocardiogr. 2015
              Jan;28(1):40-56.
              <a
                target="__blank"
                href="http://dx.doi.org/10.1016/j.echo.2014.09.009"
                >http://dx.doi.org/10.1016/j.echo.2014.09.009</a
              >
            </p>
            <p class="d-inline-block text-justify body-2 pt-3 px-3 mx-2">
              Bergamaschi V, Vignazia GL, Messina A, Colombo D, Cammarota G,
              Della Corte F, Traversi E, Paolo Navalesi P. Transthoracic
              echocardiographic assessment of cardiac output in mechanically
              ventilated critically ill patients by intensive care unit
              physicians. Brazilian Journal of Anesthesiology (English Edition),
              Volume 69, Issue 1, 2019, Pages 20-26.
              <a
                target="__blank"
                href="https://doi.org/10.1016/j.bjane.2018.09.003"
                >https://doi.org/10.1016/j.bjane.2018.09.003</a
              >
            </p>
            <p class="d-inline-block text-justify body-2 pt-3 px-3 mx-2">
              Gaspar A, Azevedo P, Roncon-Albuquerque R Jr. Non-invasive
              hemodynamic evaluation by Doppler echocardiography. Rev Bras Ter
              Intensiva. 2018 Jul-Sept; 30(3):385-393.
              <a
                target="__blank"
                href="https://www.scielo.br/j/rbti/a/gVBR7x7C5j5HmXnsxKbq5wB/?format=pdf&lang=pt"
                >https://www.scielo.br/j/rbti/a/gVBR7x7C5j5HmXnsxKbq5wB/?format=pdf&lang=pt</a
              >
            </p>
          </v-card>
          <v-divider></v-divider>
          
          <!-- Inicia codigo Contador -->
          <div align="center" class="mt-3">
            <p class="text-caption">Esta página foi visualizada
            <a
              title="Contador de Visitas do MegaContador"
              href="https://megacontador.com.br/"
              ><img
                src="https://megacontador.com.br/img-Z6nAnPywev7MJcbA-3.gif"
                border="0"
                alt="Contador de visitas"
            /></a>
            vezes</p>
          </div>
          <!-- Fim do codigo Contador -->
          <v-divider ></v-divider>
          <p class="my-5 text-caption">Desenvolvido por</p>
          <p>
            <a
              title="Logo Idea Criativa"
              href="https://www.ideacriativa.com.br/"
              target="__blank"
              >
              <img style="max-height: 80px;" src="https://ideacriativa.com.br/wp-content/uploads/2017/10/IdeaCriativa.png" alt="Idea Criativa"/>
            </a>    
          </p>
          <p class="text-caption">Autor: José Diogenes Marques Ribeiro Filho (cardiologia/ecocardiografia)
  Desenvolvedor/ ilustrador: Raul Proença</p>
          <p class="text-caption">Isenção de responsabilidade: A calculadora fornecida não devem substituir o aconselhamento profissional e não devem ser usadas para diagnóstico médico.  Todos os cálculos devem ser confirmados antes do uso clínico ou diagnóstico por profissionais médicos qualificados.  Os autores não se responsabilizam pela exatidão das informações aqui contidas.   Em nenhuma situação os autores e seus fornecedores, afiliados ou quaisquer terceiros serão responsabilizados de qualquer forma por quaisquer danos decorrentes do uso de qualquer informação fornecida.</p>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>
  <script src="https://cdn.firebase.com/js/client/2.4.2/firebase.js"></script>
  <script type="text/javascript" src="https://l2.io/ip.js?var=myip"></script>
<script>
// import Firebase from 'https://cdn.firebase.com/js/client/2.4.2/firebase.js';
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
    contador() {
      var contador = 0;
      var site_nome = "ecohemodinamicacalc"; // insira o nome do site sem usar espaco.
      var myip;
      var ip = myip;
      var f_db = new Firebase(
        "https://cliqueslinks.firebaseio.com/" + site_nome + "/"
      );
      var usuario_db = f_db.push();
      var db_presensa = new Firebase(
        "https://cliqueslinks.firebaseio.com/.info/connected/"
      );
      db_presensa.on("value", function (snap) {
        if (snap.val()) {
          usuario_db.onDisconnect().remove();
          usuario_db.set("" + ip + "");
        }
      });
      f_db.on("value", function (snap) {
        contador = snap.numChildren();
      });
      return contador;
    },
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
