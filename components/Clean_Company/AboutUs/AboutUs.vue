<template>
  <div :class="$style.about_main">
    <div :class="$style.about_box">
      <div :class="$style.about_title">
        <span></span>
        Engage audience segments and finally create actionable insights.
      </div>
      <div :class="$style.about_description">
        Our skilled, professional and trustworthy employess, who work quickly
        and efficiently, will make your life easier, if you would like to get
        rid of worries about cleaning, a professional cleaning company is a
        clear choice.
      </div>
      <div :class="$style.about_btn">
        Get an Estimate
        <img src="@/assets/imgs/arrow_right.png" />
      </div>
    </div>
    <div :class="$style.about_box">
      <div :class="$style.about_image">
        <span :class="$style.cycle1"></span>
        <span :class="$style.cycle2"></span>
        <span :class="$style.cycle3"><span></span></span>
        <img
          src="@/assets/imgs/women_jon.png"
          style="width: 58.79%; right: 0; margin-top: 26%"
        />
        <img
          src="@/assets/imgs/karpet.png"
          style="margin: 43% -12%; width: 48%"
        />
        <img src="@/assets/imgs/men.png" style="margin: 0% 9%; width: 36.1%" />
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" module>
.about_main {
  width: 100%;
  padding-bottom: 15%;
  display: flex;
}

.about_box {
  width: 45%;
  margin: 0 auto;
}
.about_title {
  font-size: 30px;
  font-weight: 400;
  margin-right: 17%;
  span {
    display: block;
    width: 65px;
    height: 5px;
    background: #31ad61;
    margin-bottom: 9%;
    margin-top: 12%;
  }
}
.about_description {
  font-weight: 100;
  margin: 11% 24% 8% 0;
  line-height: 1.4;
}

.about_btn {
  color: #31ad61;
  cursor: pointer;
  transition: all 0.3s ease;
  &:hover {
    opacity: 0.7;
  }
  img {
    margin-left: 1%;
  }
}

.about_image {
  position: relative;

  img {
    position: absolute;
    border-radius: 50%;
  }
  span {
    display: block;
    position: absolute;
    border-radius: 50%;
  }
}

.cycle1 {
  width: 17%;
  background: #ffd83b;
  padding-bottom: 17%;
  right: 30%;
  margin-top: 2.5%;
}

.cycle2 {
  width: 9%;
  background: #1cdd65;
  padding-bottom: 9%;
  right: 59%;
  margin-top: 38%;
}

.cycle3 {
  width: 26%;
  padding-bottom: 26%;
  margin-top: 10.5%;
  background: #0e6ae6;
  left: 2%;
  span {
    background: #fff;
    width: 70%;
    padding-bottom: 70%;
    margin: 15% 15%;
  }
}

@media (max-width: 700px) {
  .about_main {
    flex-wrap: wrap-reverse;
  }

  .about_box {
    width: 80%;
  }

  .about_image {
    padding-bottom: 44%;
    width: 50%;
    margin: 0 auto;
  }

  .about_title {
    margin-right: 0%;
  }
}
</style>
