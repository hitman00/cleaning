<template>
  <div :class="$style.slider_main">
    <div :class="$style.size">
      <div :class="$style.boxs">
        <div :class="$style.title">
          Professional and Affordable cleaning services in Prague
        </div>
        <div :class="$style.description">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sed enim ea
          ab praesentium veniam dolorum
        </div>
        <div :class="$style.btn">Book a Clean</div>
      </div>
      <div :class="$style.boxs">
        <div :class="$style.clean_img">
          <img src="@/assets/imgs/women.png" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Slider',
}
</script>

<style lang="scss" module>
.slider_main {
  background: #eceef0;
  padding: 0 1%;
}
.size {
  max-width: 1230px;
  margin: 0 auto;
  display: flex;
}

.boxs {
  width: 50%;
}

.title {
  font-size: 45px;
  font-weight: 600;
  margin-top: 18%;
  margin-bottom: 10%;
}

.description {
  font-size: 21px;
  font-weight: 100;
}

.btn {
  background: #31ad61;
  color: #fff;
  padding: 2%;
  max-width: max-content;
  margin-top: 10%;
  cursor: pointer;
  border-radius: 5px;
  transition: all 0.3s ease;
  &:hover {
    opacity: 0.8;
  }
}

.clean_img {
  position: relative;
  width: 69%;
  float: right;
  &:before {
    content: '';
    display: block;
    padding-bottom: 153%;
  }
  img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100%;
  }
}

@media (max-width: 900px) {
  .title {
    font-size: 35px;
  }

  .description {
    font-size: 17px;
  }
}

@media (max-width: 700px) {
  .size {
    flex-wrap: wrap;
  }

  .boxs {
    text-align: center;
    width: 100%;
  }

  .btn {
    margin: 5% auto;
  }

  .title {
    margin: 7% auto;
  }

  .clean_img {
    float: none;
    margin: 0 auto;
  }
}
</style>
