<template>
  <div class="main">
    <p class="bq">Copyright © 2024 - {{ current }}</p>
    <a class="ba" href="https://beian.miit.gov.cn/#/Integrated/index" target="_blank">
      陕ICP备2024055958号
    </a>
  </div>
</template>

<script setup lang="js">
const current = new Date().getFullYear();
</script>

<style scoped>
.main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 10px;
}

.bq {
  font-size: small;
}

.ba {
  font-size: larger;
}

a {
  text-decoration: none;
  color: #000;
}

a:hover {
  color: gray;
  text-decoration: underline;
}
</style>