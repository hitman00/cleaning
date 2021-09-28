<template>
  <div :class="$style.features_main">
    <div
      v-observe-visibility="{
        callback: visibilityChanged,
        throttle: 500,
      }"
      :class="[$style.customer, show ? $style.active : '']"
    >
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
    <div :class="[$style.customer, show ? $style.active : '']">
      <div :class="$style.box">
        <ul>
          <li style="background: #eaf7ee; color: #47a06b">
            {{ avrage }}*<span>Average Rating</span>
          </li>
          <li>{{ num }}<span>Our Cleaners</span></li>
        </ul>
        <ul style="margin-top: 10%">
          <li>{{ persent }}%<span>Success Rate</span></li>
          <li style="background: #31ad61; color: #fff">
            ${{ dollar }}<span>Avg Price Tag</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Features',
  data() {
    return {
      persent: '',
      dollar: '',
      num: 0,
      avrage: 0.1,
      show: false,
    }
  },

  // mounted() {
  //   const number = setInterval(() => {
  //     this.num++
  //     if (this.num > 123) {
  //       clearInterval(number)
  //     }
  //   }, 50)
  //   const avg = setInterval(() => {
  //     this.avrage = ((this.avrage * 10 + 0.1 * 10) / 10).toFixed(1)
  //     console.log(this.avrage)
  //     if (this.avrage >= 4.9) {
  //       clearInterval(avg)
  //     }
  //   }, 50)
  //   const per = setInterval(() => {
  //     this.persent++
  //     if (this.persent >= 56) {
  //       clearInterval(per)
  //     }
  //   }, 50)
  //   const money = setInterval(() => {
  //     this.dollar++
  //     if (this.dollar >= 20) {
  //       clearInterval(money)
  //     }
  //   }, 50)
  // },
  methods: {
    visibilityChanged(isVisible) {
      if (isVisible) {
        this.show = true
        this.test()
      }
    },
    test() {
      const money = setInterval(() => {
        this.dollar++
        if (this.dollar >= 20) {
          clearInterval(money)
        }
      }, 100)
      const per = setInterval(() => {
        this.persent++
        if (this.persent >= 56) {
          clearInterval(per)
        }
      }, 50)
      const number = setInterval(() => {
        this.num++
        if (this.num > 123) {
          clearInterval(number)
        }
      }, 30)
      const avg = setInterval(() => {
        this.avrage = ((this.avrage * 10 + 0.1 * 10) / 10).toFixed(1)
        if (this.avrage >= 4.9) {
          clearInterval(avg)
        }
      }, 50)
    },
  },
}
</script>

<style lang="scss" module>
.features_main {
  display: flex;
  justify-content: space-around;
}

.customer {
  width: 45%;
  opacity: 0;
  transition: all 0.4s ease;
  transform: translateY(100px);
  &.active {
    opacity: 1;
    transform: translateY(0px);
  }
}
.box {
  display: flex;
  justify-content: end;

  ul {
    font-size: 30px;
    margin-left: 7%;
    width: 27%;
    li {
      border: 1px solid gray;
      border-radius: 5px;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      padding: 28% 0%;
      margin: 0 -6% 10%;
      span {
        font-size: 14px;
        width: 100%;
        text-align: center;
        display: block;
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
  display: inline-block;
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

@media (max-width: 450px) {
  .customer_title {
    font-size: 16px;
  }

  .customer_description {
    font-size: 13px;
  }

  .customer_btn {
    font-size: 12px;
  }
}
</style>
