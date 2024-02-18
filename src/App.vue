<script>
import logo from "./assets/images/vue-logo.png";
import diver1 from "./assets/images/diver-1.jpg";
import diver2 from "./assets/images/diver-2.jpg";
import diver3 from "./assets/images/diver-3.jpg";
import diver4 from "./assets/images/diver-4.jpg";

import Header from "./components/Header.vue";
import Post from "./components/Post.vue";
import Buttons from "./components/Buttons.vue";
import Array from "./components/Array.vue";
import UserForm from "./components/UserForm.vue";
import ReviewForm from "./components/ReviewForm.vue";

export default {
  components: {
    Header,
    Post,
    Buttons,
    Array,
    UserForm,
    ReviewForm
  },
  data() {
    return {
      title: "Made with Love, Obsession and VueJS",
      vue_logo: logo,
      posts: [
        {
          pic: diver1,
          title: "That horizon is drifring away",
          content:
            "The sky is too blue to even portray it tomorrow. A group of people is so stragnant to me that i can't even breath. ",
        },
        {
          pic: diver2,
          title: "How long have i been sinking here?",
          content:
            "Just spit out your sadness and look ahead? I wouldn't be fine that way. Even if i turn everything against me",
        },
        {
          pic: diver3,
          title: "I would still feel a dim light!",
          content:
            "If i could get that far but it's painfull in here. Just by looking in the nights darkness. I feel like a diver struggling with the decompression",
        },
        {
          pic: diver4,
          title: "I want to make sure that I'm alive!",
          content:
            "So as I am for the deep ocean floor again, I'll breath for a moment.",
        },
      ],
      array: [34,222,535,562,1,3534],
    };
  },
};
</script>

<template>
  <Header :logo="vue_logo" :title="title"/>
  <Post :id="'post1'" :title="posts[0].title" :image="posts[0].pic" :text="posts[0].content" :isReversed="false"/>
  <Post :id="'post2'" :title="posts[1].title" :image="posts[1].pic" :text="posts[1].content" :isReversed="true"/>
  <Post :id="'post3'" :title="posts[2].title" :image="posts[2].pic" :text="posts[2].content" :isReversed="false"/>
  <Post :id="'post4'" :title="posts[3].title" :image="posts[3].pic" :text="posts[3].content" :isReversed="true"/>
  <Buttons/>
  <Array :array="array"/>
  <UserForm />
  <ReviewForm />
</template>


