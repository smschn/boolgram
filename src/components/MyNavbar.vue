<template>
  <header>

    <div class="container m-auto d-flex jc-sb ai-c">

        <img class='' src="../assets/images/logo.png" alt="Logo">

        <input class='' type="text" placeholder="Cerca">

      <div>

        <div class="nav-container-dx d-flex jc-sb ai-c">

          <i class="fa-regular fa-heart"></i>
          <i class="fa-solid fa-house-chimney"></i>

          <img src="../assets/images/profile.jpg" alt="#">

        </div>

      </div>

    </div>

  </header>
</template>

<script>
export default {
    name: 'MyNavbar'
}
</script>

<style lang="scss" scoped>

  @import '../styles/variables.scss';

  header {
    height: 70px;
    border-top: 1px solid $border;
    border-bottom: 1px solid $border;
    position: fixed;
    top: 0px;
    left: 0px;
    right: 0px;
    background-color: $bg1;

    div {
      height: 100%;

      img {
        max-height: 70%;
      }

      input {
        height: 50%;
        border: 2px solid $border;
        text-align: center;
        width: 240px;
        background-color: $bg2;
      }

      i {
        margin-right: 10px;
      }
    }

    .nav-container-dx {
      height: 70px;

      img {
        width: 30px;
        border-radius: 50%;
      }
    }
  }

</style>