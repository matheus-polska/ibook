<template>
  <footer>
    <Container class="footer-content">
      <img src="~assets/img/Logo.svg" alt="Logo" />
      <p>Copyright © 2021 IBOOK</p>
    </Container>
  </footer>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
footer {
  width: 100%;
  height: 110px;
  background: $dark;
  position: absolute;
  bottom: 0;
  left: 0;
  .footer-content {
    display: grid;
    height: 100%;
    grid-auto-flow: column;
    justify-content: space-between;
    align-items: center;
    p {
      color: $lightgray;
    }
  }
}
</style>
