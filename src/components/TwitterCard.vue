<template>
  <v-container class="tweet-container">
    <v-row justify="center">
      <v-col cols="12" md="8" lg="6">
        <v-card class="tweet-card" variant="outlined">
          <v-card-text>
            <v-row align="center">
              <v-col cols="auto">
                <v-avatar class="surface-variant" size="80">
                  <img src="https://via.placeholder.com/36" alt="Avatar" />
                </v-avatar>
              </v-col>
              <v-col cols="auto">
                <div class="tweet-content">
                  <div class="tweet-header">
                    <span class="name">{{ name }}</span>
                    <span class="username">{{ username }}</span>
                    <span class="timestamp">{{ timestamp }}</span>
                  </div>
                  <v-row>
                    <v-col cols="auto">
                      <span class="text">{{ text }}</span>
                    </v-col>
                  </v-row>
                </div>
              </v-col>
            </v-row>
          </v-card-text>
          <v-card-actions>
            <v-btn icon>
              <v-icon>mdi-comment-outline</v-icon>
            </v-btn>
            <v-btn icon>
              <v-icon>mdi-twitter-retweet</v-icon>
            </v-btn>
            <v-btn icon>
              <v-icon>mdi-heart-outline</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref, defineProps } from "vue";

defineProps({});
function useTweet() {
  const name = ref("Kanye West");
  const username = ref("@kanyewest");
  const timestamp = ref("5m");
  const text = ref(
    "I'm nice at ping pong\nI'm nice at ping pong\nI'm nice at ping pong"
  );

  return { name, username, timestamp, text };
}

const { name, username, timestamp, text } = useTweet();
</script>

<style scoped>
.tweet-card {
  max-width: 600px;
  margin-top: 50px;
  margin-bottom: 50px;
}
.tweet-content {
  margin-left: 12px;
}
.tweet-header {
  display: flex;
  align-items: center;
}
.name {
  font-weight: bold;
  margin-right: 6px;
}
.username {
  color: grey;
  margin-right: 6px;
}
.timestamp {
  color: grey;
}
.avatar {
  margin-right: 12px;
}
</style>
