<template>
  <div :class="$style.features_main">
    <div :class="$style.customer">
      <div :class="$style.hand">
        <img src="@/assets/imgs/arrow.png" />
      </div>
      <div :class="$style.customer_title">Over 1,000 satisfied customers</div>
      <div :class="$style.customer_description">
        When you live in such an amazing city as prague you need a lot of time
        to enjoy its beauty. That's why Magnnolia cleaning services are here to
        give you that time.
      </div>
      <div :class="$style.customer_btn">Book a Clean</div>
    </div>
    <div :class="$style.customer">
      <div :class="$style.box">
        <ul>
          <li style="background: #eaf7ee; color: #47a06b">
            4.9*<span>Average Rating</span>
          </li>
          <li>124<span>Our Cleaners</span></li>
        </ul>
        <ul style="margin-top: 10%">
          <li>56%<span>Success Rate</span></li>
          <li style="background: #31ad61; color: #fff">
            $20<span>Avg Price Tag</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Features',
}
</script>

<style lang="scss" module>
.features_main {
  display: flex;
  justify-content: space-around;
}

.customer {
  width: 45%;
}
.box {
  display: flex;
  justify-content: end;
  ul {
    font-size: 30px;
    margin-left: 7%;
    li {
      border: 1px solid gray;
      border-radius: 5px;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      padding: 28% 13%;
      margin: 0 -6% 10%;
      span {
        font-size: 14px;
      }
    }
  }
}

.hand {
  position: relative;
  width: 8%;
  margin: 9% 0 4.5%;
  &:before {
    content: '';
    display: block;
    padding-bottom: 100%;
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

.customer_title {
  font-size: 30px;
  font-weight: 400;
}

.customer_description {
  font-weight: 100;
  margin: 6% 11% 0 0;
  font-size: 18px;
  line-height: 1.5;
}

.customer_btn {
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

@media (max-width: 700px) {
  .features_main {
    flex-wrap: wrap;
  }

  .box {
    justify-content: center;
  }

  .customer {
    width: 90%;
    margin: 0 auto;
    text-align: center;
  }

  .hand {
    margin: 4% auto;
  }
  .customer_title {
    font-size: 25px;
  }

  .customer_description {
    margin: 3%;
    font-size: 16px;
  }

  .customer_btn {
    margin: 5% auto;
  }
}
</style>
