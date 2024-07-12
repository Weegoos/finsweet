<template>
  <q-page>
    <q-img
      src="../../assets/IndexPage/bg-main.jpg"
      :ratio="$q.screen.width < width ? 2 / 3.2 : 16 / 9"
      spinner-color="primary"
      spinner-size="82px"
    >
      <div
        class="captiontext bg-transparent q-mt-xl"
        :class="[
          $q.screen.width < width
            ? 'captionMobile q-ml-sm'
            : 'captionDesktop q-ml-xl',
        ]"
      >
        <caption style="width: 75vw">
          <p
            class="text-white text-uppercase"
            :class="[$q.screen.width < width ? 'text-h6' : 'text-h4']"
            align="left"
          >
            Posted on <span class="text-bold">startup</span>
          </p>
          <p
            class="text-bold text-white"
            :class="[$q.screen.width < width ? 'text-h5' : 'text-h3']"
            align="left"
          >
            Step-by-step guide to choosing great font pairs
          </p>
          <p
            class="text-white"
            align="left"
            :class="[$q.screen.width < width ? 'text-caption' : 'text-h5']"
          >
            By <span style="color: #ffd050">James West</span> | May 23, 2022
          </p>
          <p
            class="text-white"
            align="left"
            :class="[$q.screen.width < width ? 'text-caption' : 'text-h5']"
          >
            Duis aute irure dolor in reprehenderit in voluptate velit esse
            cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
            cupidatat non proident.
          </p>
        </caption>
        <q-btn
          style="background-color: #ffd050; width: 204px; cursor: pointer"
          no-caps
          class="q-pa-sm text-black"
          label="Read More >"
          @click="readMore"
        />
      </div>
    </q-img>
  </q-page>
</template>

<script setup>
const width = 900;
</script>

<style scoped>
.captiontextMobile {
  width: 60vw;
  position: relative;
}

.captionMobile {
  margin-top: 18vw;
}

.captionDesktop {
  margin-top: 10vw;
}
.contentMobile {
  font-size: 18px;
}

.contentDesktop {
  font-size: 28px;
}
</style>
