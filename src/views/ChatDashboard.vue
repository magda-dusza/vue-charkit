<template>
  <div class="chat-dashboard">
    <ChatNavBar />
    <b-container fluidclass="ld-over" v-bind:class="{running: loading}">
      <div class="ld ld-spin ld-ring"></div>
      <b-row>
        <b-col cols="2">
          <RoomList />
        </b-col>
        <b-col cols="7">
          <b-row>
            <b-col id="chat-content">
              <MessageList />
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <MessageForm />
            </b-col>
          </b-row>
        </b-col>
        <b-col cols="3">
          <UserList />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import ChatNavBar from "@/components/ChatNavBar.vue";
import RoomList from "@/components/RoomList.vue";
import MessageList from "@/components/MessageList.vue";
import MessageForm from "@/components/MessageForm.vue";
import UserList from "@/components/UserList.vue";
import { mapState } from "vuex";

export default {
  name: "Chat",
  components: { ChatNavBar, RoomList, MessageList, MessageForm, UserList },
  computed: {
    ...mapState(["loading"])
  }
};
</script>