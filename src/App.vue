<template>
  <main>
    <h1 v-if="showWelcome">{{ welcomeMessage }}</h1>
    <h1 v-else>sorry you are not welcome lahh</h1>
    <h2>{{ message }}</h2>
    <h3>Likes {{ likeCount }}</h3><br>
    <h3>Dislikes {{ dislikeCount }}</h3><br>
    <button @click="incrementNumber">Like</button>
    <button @click="decrementNumber">Unlike</button>
    <hr>
    <div v-for="student in students" :key="student">
      {{ student }}
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      message: "We love Vue.",
      welcomeMessage: "Welcome Everyone daahhhh !",
      likeCount: 0,
      dislikeCount: 0,
      showWelcome: true,
      students: ["Allen", "Jake", "John"],
    };
  },
  mounted() {
    console.log("Mounted");
    console.log("message >>" + this.message);
    console.log("showWelcome", this.showWelcome);
    this.likeCount = 0;
    this.dislikeCount = 0; // 
  },
  created() {
    console.log("Created");
  },
  methods: {
    incrementNumber() {
      console.log("Call increment Method");
      this.likeCount += 1;
      this.showWelcome = true; // Change the title to "Welcome"
    },
    decrementNumber() {
      console.log("Call decrement Method");
      this.dislikeCount += 1;
      this.showWelcome = false; // Change the title to "You are not welcome"
    },
  },
};
</script>
