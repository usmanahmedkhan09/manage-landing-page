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
          <div class="index">0{{ index + 1 }}</div>
          <div class="feature">
            <p class="feature__title">{{ feature.title }}</p>
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
          class="views__container--details"
          v-for="(view, index) in views"
          :key="index"
        >
          <div class="image__wrapper">
            <img :src="getImageUrl(view.pic)" alt="" />
          </div>
          <p class="name">{{ view.name }}</p>
          <q class="view">{{ view.views }}</q>
        </div>
      </div>
      <button class="btn">Get Started</button>
    </div>
  </main>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const features = ref([
      {
        title: "Track company-wide progress",
        description:
          "See how your task fit into the wider vision.Gor from tracking progress at the milestone level all the way done to the smallest of details.Never lose sight of bigger picture again",
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

    const views = ref([
      {
        name: "anisha li",
        pic: "avatar-anisha.png",
        views:
          "Manage has supercharged our team's workflow.The ability to maintain visibility on large milestone at all times keeps everyone motivated.",
      },
      {
        name: "ali bravo",
        pic: "avatar-ali.png",
        views:
          "we have been able to cancel so many other subscriptions since using Manage.There is no more cross-channel confusion and everyone is much more focused.",
      },
      {
        name: "richard watts",
        pic: "avatar-richard.png",
        views:
          "Manage allow us to provide structure and processes.It keeps organized and focused.I can't stop recommending Them to everyone I talk to!",
      },
      {
        name: "shanai gough",
        pic: "avatar-shanai.png",
        views:
          "Their software allows us to track, manage and collaborate on our projects from anywhere.It keeps the whole team in-sync without being intrusive",
      },
    ]);

    const getImageUrl = (name: any) => {
      return new URL(`../../assets/images/${name}`, import.meta.url).href;
    };
    return { features, views, getImageUrl };
  },
});
</script>
