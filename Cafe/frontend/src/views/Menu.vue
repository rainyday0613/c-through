<template>
  <v-card color="basil" >
    <v-card-title class="text-center justify-center py-6">
      <h1 class="font-weight-bold display-3 basil--text">Menu</h1>
      <v-btn id="hoi">주문하기</v-btn>
    </v-card-title>
    <v-tabs
        v-model="tab"
        background-color="transparent"
        color="black"
        grow
    >
      <v-tab
          v-for="item in items"
          :key="item"
      >
        {{ item }}
      </v-tab>
    </v-tabs>
    <v-tabs-items v-model="tab">
      <v-tab-item
          v-for="item in items"
          :key="item"
      >
        <v-card
            color="basil"
            flat
            v-if="item === 'Coffee with Caffeine'"
        >
          <CardGrid :events="events1" :buttonText="'Register'" @buttonClicked="eventHandler" />
        </v-card>

        <v-card
            color="basil"
            flat
            v-if="item === 'Coffee with no Caffeine'"
        >
          <CardGrid :events="events2" :buttonText="'Register'" @buttonClicked="eventHandler" />
        </v-card>

        <v-card
            color="basil"
            flat
            v-if="item === 'Juice'"
        >
          <CardGrid :events="events3" :buttonText="'Register'" @buttonClicked="eventHandler" />
        </v-card>

        <v-card
            color="basil"
            flat
            v-if="item === 'Tea'"
        >
          <CardGrid :events="events4" :buttonText="'Register'" @buttonClicked="eventHandler" />
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>

<script>
import CardGrid from "@/components/Card/CardGrid";
export default {
  name: "Menu",
  components: {
    CardGrid
  },
  data () {
    return {
      tab: null,

      items: [
        'Coffee with Caffeine', 'Coffee with no Caffeine', 'Juice', 'Tea'
      ],
      events1: [
        {
          name: "아메리카노",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          html:
              "<br><p>This paragraph is created using <br> custom <br> HTML</p>",
          outerImage: "https://lh3.googleusercontent.com/proxy/7jnrhIHRr0fW4gwXJU_J4UxLcmbwWVJAQau0DeCG7ggzi353272lRM9OtxZwp0mUTWpYtUG5Zymqk1T3PLzWE6PF7O-b6ksK3j_UKu9Uglck_Xn-2jw1iBfnjTCrx4teaLz3LhiEPu-XuKTqLMew9WcevSB0egnk2qhVtJWTdDPRrukqsJIqEFTvSl4zXg5GLMh5WvlxYW3cl6Em2sgP3qgVU8Z5Uz-aLJ-JZuQIsKyvlOckoLcBsGTw2oDSvNA7TIW75Z42R1nT2GDABd3Af8KP6a2Ypr5LAPsjyokYh59H7-mTgYNtB4Ra11H4yPFk2GuhY4urso99wNCbYhi0NHVz6doHI0FXR-7evQh9tdTqrrU",
          innerImage: "assets/images/1.jpg",
          details: {
            "Team Size": "2",
            Time: "10AM - 1PM"
          }
        },
        {
          name: "콜드브루",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/2.jpg",
          innerImage: "assets/images/hackathon.jpg",
          details: {
            "Team Size": "2",
            Time: "12PM - 8PM"
          }
        },
        {
          name: "카페라떼",
          date: "October 12, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/3.jpg",
          innerImage: "assets/images/treasure.jpg",
          details: {
            "Team Size": "2",
            Time: "4PM - 6PM"
          }
        },
        {
          name: "바닐라라떼",
          date: "October 13, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/4.jpg",
          innerImage: "assets/images/marvel.jpg",
          details: {
            "Team Size": "2",
            Time: "3PM - 5PM"
          }
        },
        {
          name: "카라멜 마끼야또",
          date: "October 13, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/4.jpg",
          innerImage: "assets/images/marvel.jpg",
          details: {
            "Team Size": "2",
            Time: "3PM - 5PM"
          }
        },
        {
          name: "카푸치노",
          date: "October 13, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/4.jpg",
          innerImage: "assets/images/marvel.jpg",
          details: {
            "Team Size": "2",
            Time: "3PM - 5PM"
          }
        },
        {
          name: "에스프레소",
          date: "October 13, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/4.jpg",
          innerImage: "assets/images/marvel.jpg",
          details: {
            "Team Size": "2",
            Time: "3PM - 5PM"
          }
        }
      ],
      events2: [
        {
          name: "아메키라노",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          html:
              "<br><p>This paragraph is created using <br> custom <br> HTML</p>",
          outerImage: "https://lh3.googleusercontent.com/proxy/7jnrhIHRr0fW4gwXJU_J4UxLcmbwWVJAQau0DeCG7ggzi353272lRM9OtxZwp0mUTWpYtUG5Zymqk1T3PLzWE6PF7O-b6ksK3j_UKu9Uglck_Xn-2jw1iBfnjTCrx4teaLz3LhiEPu-XuKTqLMew9WcevSB0egnk2qhVtJWTdDPRrukqsJIqEFTvSl4zXg5GLMh5WvlxYW3cl6Em2sgP3qgVU8Z5Uz-aLJ-JZuQIsKyvlOckoLcBsGTw2oDSvNA7TIW75Z42R1nT2GDABd3Af8KP6a2Ypr5LAPsjyokYh59H7-mTgYNtB4Ra11H4yPFk2GuhY4urso99wNCbYhi0NHVz6doHI0FXR-7evQh9tdTqrrU",
          innerImage: "assets/images/1.jpg",
          details: {
            "Team Size": "2",
            Time: "10AM - 1PM"
          }
        },
        {
          name: "카페라떼",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/2.jpg",
          innerImage: "assets/images/hackathon.jpg",
          details: {
            "Team Size": "2",
            Time: "12PM - 8PM"
          }
        },
        {
          name: "Treasure Hunt",
          date: "October 12, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/3.jpg",
          innerImage: "assets/images/treasure.jpg",
          details: {
            "Team Size": "2",
            Time: "4PM - 6PM"
          }
        },
        {
          name: "Marvel Quiz",
          date: "October 13, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/4.jpg",
          innerImage: "assets/images/marvel.jpg",
          details: {
            "Team Size": "2",
            Time: "3PM - 5PM"
          }
        }
      ],
      events3: [
        {
          name: "아메키라노",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          html:
              "<br><p>This paragraph is created using <br> custom <br> HTML</p>",
          outerImage: "https://lh3.googleusercontent.com/proxy/7jnrhIHRr0fW4gwXJU_J4UxLcmbwWVJAQau0DeCG7ggzi353272lRM9OtxZwp0mUTWpYtUG5Zymqk1T3PLzWE6PF7O-b6ksK3j_UKu9Uglck_Xn-2jw1iBfnjTCrx4teaLz3LhiEPu-XuKTqLMew9WcevSB0egnk2qhVtJWTdDPRrukqsJIqEFTvSl4zXg5GLMh5WvlxYW3cl6Em2sgP3qgVU8Z5Uz-aLJ-JZuQIsKyvlOckoLcBsGTw2oDSvNA7TIW75Z42R1nT2GDABd3Af8KP6a2Ypr5LAPsjyokYh59H7-mTgYNtB4Ra11H4yPFk2GuhY4urso99wNCbYhi0NHVz6doHI0FXR-7evQh9tdTqrrU",
          innerImage: "assets/images/1.jpg",
          details: {
            "Team Size": "2",
            Time: "10AM - 1PM"
          }
        },
        {
          name: "카페라떼",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/2.jpg",
          innerImage: "assets/images/hackathon.jpg",
          details: {
            "Team Size": "2",
            Time: "12PM - 8PM"
          }
        },
        {
          name: "Treasure Hunt",
          date: "October 12, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/3.jpg",
          innerImage: "assets/images/treasure.jpg",
          details: {
            "Team Size": "2",
            Time: "4PM - 6PM"
          }
        },
        {
          name: "Marvel Quiz",
          date: "October 13, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/4.jpg",
          innerImage: "assets/images/marvel.jpg",
          details: {
            "Team Size": "2",
            Time: "3PM - 5PM"
          }
        }
      ],
      events4: [
        {
          name: "아메키라노",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          html:
              "<br><p>This paragraph is created using <br> custom <br> HTML</p>",
          outerImage: "https://lh3.googleusercontent.com/proxy/7jnrhIHRr0fW4gwXJU_J4UxLcmbwWVJAQau0DeCG7ggzi353272lRM9OtxZwp0mUTWpYtUG5Zymqk1T3PLzWE6PF7O-b6ksK3j_UKu9Uglck_Xn-2jw1iBfnjTCrx4teaLz3LhiEPu-XuKTqLMew9WcevSB0egnk2qhVtJWTdDPRrukqsJIqEFTvSl4zXg5GLMh5WvlxYW3cl6Em2sgP3qgVU8Z5Uz-aLJ-JZuQIsKyvlOckoLcBsGTw2oDSvNA7TIW75Z42R1nT2GDABd3Af8KP6a2Ypr5LAPsjyokYh59H7-mTgYNtB4Ra11H4yPFk2GuhY4urso99wNCbYhi0NHVz6doHI0FXR-7evQh9tdTqrrU",
          innerImage: "assets/images/1.jpg",
          details: {
            "Team Size": "2",
            Time: "10AM - 1PM"
          }
        },
        {
          name: "카페라떼",
          date: "October 11, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/2.jpg",
          innerImage: "assets/images/hackathon.jpg",
          details: {
            "Team Size": "2",
            Time: "12PM - 8PM"
          }
        },
        {
          name: "Treasure Hunt",
          date: "October 12, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/3.jpg",
          innerImage: "assets/images/treasure.jpg",
          details: {
            "Team Size": "2",
            Time: "4PM - 6PM"
          }
        },
        {
          name: "Marvel Quiz",
          date: "October 13, 2019",
          description:
              "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem veritatis ea sint voluptatum vel rerum ipsum illo architecto repellat debitis corporis ex, ut explicabo! Voluptatum commodi dignissimos nihil cumque mollitia?",
          outerImage: "assets/images/4.jpg",
          innerImage: "assets/images/marvel.jpg",
          details: {
            "Team Size": "2",
            Time: "3PM - 5PM"
          }
        }
      ],
      methods: {
        eventHandler() {
          console.log('button clicked');
        }
      }
    }
  }
}
</script>

<style scoped>
.basil {
  background-color: #FFFBE6;
}
.basil--text {
  color: #356859;
}

#hoi {
  display: flex;
  padding: 0 24px 0 24px;
  left: 600px;
  font-size: 22px;
  color: #356859;
  border-radius: 5px;
  font-weight: bold;
}
@media only screen and (max-width: 768px) {
  .title {
    font-size: 10vw;
  }
}

div.card {
  margin: 40px 40px;
}

</style>
