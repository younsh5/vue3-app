<template>
  <header>
    <img src="https://cphoto.asiae.co.kr/listimglink/1/2019111514322784703_1573795947.png" alt="Logo" />
    <span class="toggle" @click="toggleSidebar"><font-awesome-icon :icon="['fas', 'bars']" bounce /></span>
    <ul>
      <li @click="IFMonitoring"><router-link to="/dashboard">IF 모니터링</router-link></li>
    </ul>
    <ul>
      <li><router-link to="/dashboard">통계</router-link></li>
    </ul>
  </header>
</template>

<script>
export default {
  methods: {
    toggleSidebar() {
      this.$emit('toggle');
    },
    IFMonitoring() {
      this.$router.push('/monitoring/interface');
    },
  }
};
</script>

<style scoped>
img {
  height: 55px;
}

header {
  background-color: white;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 60px;
  z-index: 1000;
  display: flex;
  padding: 0;
  border-bottom: 1px solid #c2c2c2;
  align-items: center;
}

span {
  margin-left: 15px;
}

header > ul {
  list-style: none;
  color: #808080;
}

header > ul > li {
  float: left;
  margin-right: 10px;
  font-size: 17px;
}
header > ul > li a {
  font-weight: bolder;
  color: #808080;
  text-decoration: none;
}

header > ul > li a:hover,
header > ul > li a:active {
  color: #000000;
}
header > ul > li:hover,
header > ul > li:active {
  color: #000000;
}

.toggle {
  font-size: 26px;
  color: #808080;
}

.toggle:hover,
.toggle:active {
  cursor: pointer;
  color: #000000;
}
</style>
