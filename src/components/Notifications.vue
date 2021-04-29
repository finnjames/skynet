<!--
class EventNotification(Base):
  __tablename__ = 'event_notifications'

  id = Column(Integer, primary_key=True)
  event_id = Column(ForeignKey('events.id'))
  subscription_id = Column(ForeignKey('event_subscriptions.id'))
  is_deleted = Column(Boolean, nullable=False, default=False)
  created_on =  Column(DateTime, default=datetime.datetime.utcnow)
  email_sent_on = Column(DateTime)
  email_attempts = Column(Integer, nullable=False, default=0)
  sms_sent_on = Column(DateTime)
  sms_attempts = Column(Integer, nullable=False, default=0)

  event = relationship('Event', uselist=False)
  subscription = relationship('EventSubscription', uselist=False)
-->

<template>
  <section>
    <button
      class="button"
      @click="notificationModalActive = !notificationModalActive"
    >
      <span class="material-icons">notifications</span>
      <span
        title="badge"
        class="badge"
        v-show="this.number_of_notifications > 0"
        >{{ this.number_of_notifications }}</span
      >
    </button>

    <div
      v-show="notificationModalActive"
      class="modal"
      :class="{ 'is-active': notificationModalActive }"
    >
      <div
        class="modal-background"
        @click="notificationModalActive = false"
      ></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title">Notifications</p>
        </header>
        <section class="modal-card-body">
          <!-- notifications -->
          <div
            v-for="n in notificationList"
            :key="n.title"
            class="notification"
          >
            <button class="delete" @click="n.active = false"></button>
            <p>
              <strong>{{ n.title }}</strong>
            </p>
            <p>{{ n.message }}</p>
          </div>
          <div v-if="this.number_of_notifications <= 0">
            No more notifications!
          </div>
        </section>
        <footer class="modal-card-foot">
          <button class="button" @click="notificationModalActive = false">
            Close
          </button>
        </footer>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
  import { Component, Prop, Vue } from "vue-property-decorator";

  @Component
  export default class Navbar extends Vue {
    notificationModalActive = false;
    notificationData = [
      { title: "hello", message: "world", active: true },
      { title: "infernus", message: "ad astra", active: true },
      { title: "hey", message: "jude", active: true }
    ];
    get notificationList(): Array<Object> {
      return this.notificationData.filter((a) => a.active);
    }
    get number_of_notifications(): number {
      return this.notificationList.length
    };
  }
</script>

<style lang="scss">
  @import "@/scss/_variables.scss";

  .badge {
    position: absolute;
    top: -12px;
    right: -14px;
    padding: 1px 9px;
    border-radius: 1024px;
    background-color: $primary;
    color: $white;
    z-index: 1;
  }
</style>
