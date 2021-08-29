<template>
  <div :class="$style.header_main">
    <div :class="$style.box">
      <div :class="$style.logo">
        <img src="@/assets/imgs/logo.png" />
      </div>
      <div :class="$style.meno_bar">
        <img src="@/assets/imgs/meno_icon.png" />
        <ul>
          <li>Home</li>
          <li>Cleaning Services</li>
          <li>Prices</li>
          <li>Blog</li>
          <li>Book Now</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="scss" module>
.header_main {
  background: #eceef0;
  padding: 0 1%;
}

.box {
  max-width: 1230px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 2% 0;
}

.meno_bar {
  width: 70%;
  display: flex;
  font-weight: 400;
  justify-content: flex-end;
  transition: all 0.4s ease;
  ul {
    width: 100%;
    display: flex;
    justify-content: flex-end;
    li {
      padding: 1.5% 2%;
      border-radius: 5px;
      transition: all 0.4s ease;
      &:hover {
        background: #31ad61;
        color: #fff;
      }
    }
  }
  img {
    display: none;
    width: 26px;
    cursor: pointer;
  }
  &:hover {
    opacity: 0.7;
  }
}

.logo {
  position: relative;
  width: 80px;
  &:before {
    display: block;
    content: '';
    padding-bottom: 50%;
  }
  img {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    width: 100%;
  }
}

@media (max-width: 900px) {
  .meno_bar {
    margin-right: 8%;
    ul {
      display: none;
    }
    img {
      display: block;
    }
  }
}
</style>
