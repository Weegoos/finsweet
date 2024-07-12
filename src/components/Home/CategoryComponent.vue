<template>
  <div style="padding-top: 45px">
    <div class="catagory">
      <p class="text-h4 text-bold text-center">Choose A Catagory</p>
      <div
        class="card q-gutter-lg"
        :class="[$q.screen.width < 1050 ? 'column q-pa-xl' : 'row q-ml-lg']"
      >
        <div v-for="category in catagory" :key="category.headline">
          <q-item
            class="shadow-1"
            v-ripple
            :class="[$q.screen.width < 1050 ? '' : 'my-card']"
          >
            <div>
              <img class="q-ma-md" :src="category.img" />
              <q-card-section>
                <div>
                  <p class="text-h6 text-bold">{{ category.headline }}</p>
                  <p class="text-body1">{{ category.description }}</p>
                </div>
              </q-card-section>
            </div>
          </q-item>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Business from "../../assets/IndexPage/Business.svg";
import Economy from "../../assets/IndexPage/Economy.svg";
import Startup from "../../assets/IndexPage/Startup.svg";
import Technology from "../../assets/IndexPage/tech.svg";

const catagory = [
  {
    img: Business,
    headline: "Business",
    description: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit.",
  },
  {
    img: Startup,
    headline: "Startup",
    description: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit.",
  },
  {
    img: Economy,
    headline: "Economy",
    description: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit.",
  },
  {
    img: Technology,
    headline: "Technology",
    description: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit.",
  },
];
</script>

<style scoped>
.my-card {
  height: 0px auto;
  width: 21vw;
  cursor: pointer;
}

.my-card:hover {
  background-color: #ffd050;
  transition: 0.7s ease;
}

.my-card img {
  height: 100px;
  width: 100px;
  padding: 5px;
  background-color: #fbf6ea;
  border-radius: 7px;
}
</style>
