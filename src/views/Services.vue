<template>
  <v-layout column>
    <v-flex xs12 sm6>
      <v-card>
        <v-container
          fluid
          grid-list-md
        >
          <v-layout row wrap>
            <v-flex
              v-for="card in cards"
              v-bind="{ [`xs${card.flex}`]: true }"
              :key="card.title"
            >
              <v-card>
                <v-img
                  :src="card.src"
                  height="400px"

                >
                  <v-container
                    fill-height
                    fluid
                    pa-2
                  >
                    <v-layout fill-height>
                      <v-flex xs12 align-end flexbox>
                        <span class="headline white--text" v-text="card.title"></span>
                      </v-flex>
                    </v-layout>
                  </v-container>
                </v-img>

                <v-card-actions dark>
                  <v-spacer></v-spacer>
                  <v-btn icon>
                    <v-icon>fas fa-heart</v-icon>
                  </v-btn>
                  <v-btn icon>
                    <v-icon>fas fa-bookmark</v-icon>
                  </v-btn>
                  <v-btn icon>
                    <v-icon>fas fa-share-alt</v-icon>
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    data: () => ({
      cards: [
        { title: 'Dream Big', src: require('../assets/img/adult-barbell-body-17840.jpg'), flex: 12 },
        { title: 'Be Beautiful', src: require('../assets/img/pexels-photo-799420.jpeg'), flex: 12 },
        { title: 'Work Hard', src: require('../assets/img/cross-2276772_1920.jpg'), flex: 12 },
        { title: 'Share Your Reflections', src: require('../assets/img/ladyincity.jpeg'), flex: 12 }
      ]
    })
  }
</script>
