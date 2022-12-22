<template>
  <main class="content">
    <div class="content__intro">
      <div class="content__intro--details">
        <h1>
          Bring everyone <br />
          together to build
          <br />
          better products.
        </h1>
        <p>
          Manage makes it simple for software teams <br />
          to plane day-to-day tasks while keeping the <br />larger team goals in
          view.
        </p>
        <button class="btn">Get Started</button>
      </div>
      <div class="content__intro--image">
        <img src="../../assets/images/illustration-intro.svg" alt="" />
      </div>
    </div>
    <div class="content__features">
      <div class="content__features--question">
        <h1 class="question">
          What's different about
          <br />
          Manage?
        </h1>
        <p class="answer">
          Manage provide all the functionality your <br />team needs, without
          the complexity.Our <br />
          software is tailor-made for modren digital<br />
          products teams
        </p>
      </div>
      <div class="content__features--details">
        <div
          class="feature__wrapper"
          v-for="(feature, index) in features"
          :key="index"
        >
          <div class="index__wrapper">
            <div class="index">0{{ index + 1 }}</div>
            <p class="title">{{ feature.title }}</p>
          </div>
          <div class="feature">
            <!-- <p class="feature__title">{{ feature.title }}</p> -->
            <p class="feature__des">
              {{ feature.description }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="content__views">
      <h2 class="content__views--title">What they've said</h2>
      <div class="views__container">
        <div
          class="views__container--details fade"
          v-for="(view, index) in filteredviews"
          :key="index"
          :class="view.id == selectedViewIndex ? 'active' : ''"
        >
          <div class="image__wrapper">
            <img :src="getImageUrl(view.pic)" alt="" />
          </div>
          <p class="name">{{ view.name }}</p>
          <q class="view">{{ view.views }}</q>
        </div>
        <div class="views__container--dots">
          <div
            class="dot"
            v-for="num in [0, 1, 2, 3]"
            :key="num"
            :class="num == selectedViewIndex ? 'active' : ''"
          ></div>
        </div>
      </div>
      <button class="btn">Get Started</button>
    </div>
    <div class="content__support">
      <h1>
        Simplify how your team <br />
        works today.
      </h1>
      <button class="btn">Get Started</button>
    </div>
  </main>
</template>
<script lang="ts">
import { defineComponent, ref, computed, onMounted } from "vue";

export default defineComponent({
  setup() {
    const features = ref([
      {
        title: "Track company-wide progress",
        description:
          "See how your day-to-task fit into the wider vision.Our from tracking progress at the milestone level all the way done to the smallest of details.Never lose sight of bigger picture again",
      },
      {
        title: "Advance built-in reports",
        description:
          "Set internal delivery estimates and track progress toward company goals.Our customisable dashboard helps you build out the reports you need to keep key stackholders informed",
      },
      {
        title: "Everything you need in one place",
        description:
          "Stop jumping from one service to another to communicate, store files,track tasks and share documents.Manage offer an all-in-one team productivity solution",
      },
    ]);

    const views = ref<any>([
      {
        id: 0,
        name: "anisha li",
        pic: "avatar-anisha.png",
        views:
          "Manage has supercharged our team's workflow.The ability to maintain visibility on large milestone at all times keeps everyone motivated.",
      },
      {
        id: 1,
        name: "ali bravo",
        pic: "avatar-ali.png",
        views:
          "we have been able to cancel so many other subscriptions since using Manage.There is no more cross-channel confusion and everyone is much more focused.",
      },
      {
        id: 2,
        name: "richard watts",
        pic: "avatar-richard.png",
        views:
          "Manage allow us to provide structure and processes.It keeps organized and focused.I can't stop recommending Them to everyone I talk to!",
      },
      {
        id: 3,
        name: "shanai gough",
        pic: "avatar-shanai.png",
        views:
          "Their software allows us to track, manage and collaborate on our projects from anywhere.It keeps the whole team in-sync without being intrusive",
      },
    ]);

    const selectedViewIndex = ref(0);

    let filteredviews = computed(() => {
      return [views.value[selectedViewIndex.value]];
    });

    const moveViews = () => {
      if (selectedViewIndex.value >= views.value.length - 1) {
        selectedViewIndex.value = 0;
      } else {
        selectedViewIndex.value += 1;
      }
      setTimeout(moveViews, 2000);
    };

    onMounted(() => {
      setTimeout(moveViews, 2000);
    });
    const getImageUrl = (name: any) => {
      return new URL(`../../assets/images/${name}`, import.meta.url).href;
    };
    return { features, views, getImageUrl, selectedViewIndex, filteredviews };
  },
});
</script>
