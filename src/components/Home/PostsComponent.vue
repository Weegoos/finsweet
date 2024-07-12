<template>
  <div class="q-mt-xl">
    <div>
      <div
        class="q-gutter-md"
        :class="[$q.screen.width < width ? 'column' : 'row']"
      >
        <div class="col">
          <p class="text-bold text-h4">Featured Post</p>
          <q-card class="my-card">
            <q-img src="../../assets/IndexPage/homePost.jpg" :ratio="16 / 9" />
            <q-card-section>
              <div class="text-body2">By John Doe | May 23, 2022</div>
              <div class="text-h6">
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
              </div>
            </q-card-section>
            <q-card-section>
              Duis aute irure dolor in reprehenderit in voluptate velit esse
              cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
              cupidatat non proident.
            </q-card-section>
            <q-card-actions>
              <q-btn
                no-caps
                label="Read More >"
                style="background-color: #ffd050"
              />
            </q-card-actions>
          </q-card>
        </div>
        <div class="col">
          <span class="text-bold text-h4">All Post</span>
          <q-btn
            flat
            no-caps
            label="View All"
            @click="onClick"
            style="color: #592ea9"
            class="q-mb-md float-right"
          />
          <q-list>
            <q-item clickable v-ripple v-for="n in 4" :key="n">
              <q-item-section>
                <p class="text-caption">
                  By <span style="color: #592ea9"> John Deo</span> | Aug 23,
                  2021
                </p>
                <p class="text-h4 text-bold">
                  8 Figma design systems that you can download for free today.
                </p>
              </q-item-section>
            </q-item>
          </q-list>
        </div>
      </div>
    </div>

    <div class="q-mt-xl">
      <div>
        <div class="row" style="height: 25px">
          <div class="col bg-white"></div>
          <div class="col-6" style="background-color: #ffd050"></div>
          <div class="col bg-purple"></div>
        </div>
        <div
          class="q-pa-xl"
          :class="[$q.screen.width < width ? 'column ' : 'row']"
          style="height: 0px auto; background-color: #f4f0f8"
        >
          <div class="col">
            <p class="text-body1 text-uppercase">About us</p>
            <p class="text-h4">
              We are a community of content writers who share their learnings
            </p>
            <p class="text-body2">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </p>
          </div>
          <div class="col">
            <p class="text-body1 text-uppercase">Our mission</p>
            <p class="text-h4">
              Creating valuable content for creatives all around the world
            </p>
            <p class="text-body2">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat.
            </p>
          </div>
        </div>
        <div style="background-color: #f4f0f8" class="q-pl-xl">
          <q-btn
            flat
            no-caps
            color="purple"
            label="Read more >"
            @click="readMore"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const width = 900;
</script>

<style></style>
