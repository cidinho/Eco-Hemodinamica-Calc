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
                    color="success"
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
<<<<<<< HEAD
export default {
  name: "HelloWorld",

  data: () => ({
    peso: "",
    altura: "",
  }),
  computed: {
    asc() {
      // return 0.007184*(this.peso^0.725)*(this.altura^0.425);
      return (
        0.007184 * Math.pow(this.altura, 0.725) * Math.pow(this.peso, 0.425)
      );
    },
  },
};
=======
  export default {
    name: 'HelloWorld',

    data: () => ({
      ecosystem: [
        {
          text: 'vuetify-loader',
          href: 'https://github.com/vuetifyjs/vuetify-loader',
        },
        {
          text: 'github',
          href: 'https://github.com/vuetifyjs/vuetify',
        },
        {
          text: 'awesome-vuetify',
          href: 'https://github.com/vuetifyjs/awesome-vuetify',
        },
      ],
      importantLinks: [
        {
          text: 'Documentation',
          href: 'https://vuetifyjs.com',
        },
        {
          text: 'Chat',
          href: 'https://community.vuetifyjs.com',
        },
        {
          text: 'Made with Vuetify',
          href: 'https://madewithvuejs.com/vuetify',
        },
        {
          text: 'Twitter',
          href: 'https://twitter.com/vuetifyjs',
        },
        {
          text: 'Articles',
          href: 'https://medium.com/vuetify',
        },
      ],
      whatsNext: [
        {
          text: 'Explore components',
          href: 'https://vuetifyjs.com/components/api-explorer',
        },
        {
          text: 'Select a layout',
          href: 'https://vuetifyjs.com/getting-started/pre-made-layouts',
        },
        {
          text: 'Frequently Asked Questions',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
      ],
    }),
  }
>>>>>>> c5ae6e51cc1b61f5b9fb539c08f111b1dc843278
</script>
