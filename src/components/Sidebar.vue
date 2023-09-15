<template>
  <aside :class="{ 'is-hidden': !active }">
    <h4>
      DASHBOARD
    </h4>
    <ul @click="Dashboard">
      <li><font-awesome-icon :icon="['fas', 'chart-line']" class="icon" />대시보드</li>
    </ul>
    <h4>
      모니터링
    </h4>
    <ul @click="IFMonitoring">
      <li><font-awesome-icon :icon="['fas', 'chart-line']" class="icon" />I/F 모니터링</li>
    </ul>
    <ul @click="SocketMonitoring">
      <li><font-awesome-icon :icon="['fas', 'desktop']" class="icon" />Socket 모니터링</li>
    </ul>
    <ul @click="APIMonitoring">
      <li><font-awesome-icon :icon="['fas', 'desktop']" class="icon" />API 모니터링</li>
    </ul>
    <h4>
      통계
    </h4>
    <ul @click="Dashboard">
      <li><font-awesome-icon :icon="['fas', 'clock']" class="icon" />I/F 통계</li>
    </ul>
  </aside>
</template>


<script>
export default {
  props: {
    active: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    Dashboard() {
      this.$router.push('/dashboard/adminDashboard');
    },
    IFMonitoring() {
      this.$router.push('/monitoring/interface');
    },
    SocketMonitoring() {
      this.$router.push('/monitoring/socket');
    },
    APIMonitoring() {
      this.$router.push('/monitoring/api');
    }
  }
};
</script>

<style scoped>
aside {
  padding-top: 60px;
  width: 225px;
  height: 100vh;
  background-color: #02292a;
  color: white;
  position: fixed;
  top: 0;
  left: 0;
  transition: transform 0.3s ease-out;
  transform: translateX(0);
}

aside.is-hidden {
  transform: translateX(-100%);
}

h4 {
  padding: 18px;
  font-size: 13px;
  font-weight: bolder;
}

ul {
  margin-left: -20px;
  font-size: 16px;
}
li {
  list-style: none;
  padding-top: 10px;
  padding-bottom: 10px;
}
ul:hover {
  cursor: pointer;
  background-color: #2c3e50;
}
.icon {
  margin-right: 14px;
}
</style>
