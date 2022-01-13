<template>
  <v-app id="inspire">
    <v-app-bar app color="white" flat>
      <v-container class="py-0 fill-height">
        <v-avatar class="mr-10" color="grey darken-1" size="32"></v-avatar>

        <v-btn v-for="link in links" :key="link" text>
          {{ link }}
        </v-btn>

        <v-spacer></v-spacer>

        <v-responsive max-width="260">
          <v-text-field
            dense
            flat
            hide-details
            rounded
            solo-inverted
          ></v-text-field>
        </v-responsive>
      </v-container>
    </v-app-bar>

    <v-main class="grey lighten-3">
      <v-container>
        <v-row>
          <v-col cols="4">
            <v-sheet rounded="lg">
              <v-list color="transparent">
                <ColorPicker />
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title
                      v-for="(xyz, index) in axis"
                      :key="index"
                    >
                      {{ xyz }} =
                      <v-btn-toggle mandatory>
                        <v-btn @click="++xyz">
                          <v-icon> mdi-plus</v-icon>
                        </v-btn>
                        <v-btn @click="--xyz">
                          <v-icon> mdi-minus</v-icon>
                        </v-btn>
                      </v-btn-toggle>
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>

                <v-divider class="my-2"></v-divider>

                <v-list-item link color="grey lighten-4">
                  <v-list-item-content>
                    <v-list-item-title> Refresh </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </v-sheet>
          </v-col>

          <v-col>
            <v-sheet min-height="70vh" rounded="lg">
              <Render />

              <!--  -->
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>


<script>
import Render from "./components/Render.vue";
import ColorPicker from "./components/ColorPicker.vue";
export default {
  components: { Render, ColorPicker },
  data: () => ({
    links: ["Dashboard", "Messages", "Profile", "Updates"],
    axis: ["x", "y", "z"],
    toggle_exclusive: undefined,
  }),
};
</script>