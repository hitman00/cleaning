<template>
  <div :class="$style.branding_main">
    <div
      v-observe-visibility="{
        callback: visibilityChanged,
        throttle: 500,
      }"
      :class="[$style.brands_box, show ? $style.active : '']"
    >
      <div :class="$style.images">
        <img
          :class="show ? $style.image_active : ''"
          src="@/assets/imgs/women_cleaner3.png"
          style="margin-top: 50%; transform: translateX(300px)"
        />
        <!-- prettier-ignore-attribute -->
        <img
          :class="show ? $style.image_active : ''"
          src="@/assets/imgs/women_cleaner.png"
          style="transform: translateY(-400px);transition-delay: 0.5s;margin: 0 34% 0;"
        />
        <!-- prettier-ignore-attribute -->
        <img
          :class="show ? $style.image_active : ''"
          src="@/assets/imgs/women_cleaner2.png"
          style="transform: translateX(-400px);transition-delay: 1s;margin: 53% 0 0 66%;"
        />
      </div>
    </div>
    <div :class="[$style.brands_box, show ? $style.active : '']">
      <div :class="$style.fix_size">
        <div :class="$style.brand_title">
          Demonstrate branding to, consequently
        </div>
        <div :class="$style.brand_description">
          Demonstrate branding to, consequently, think outside the box. Take
          customer experience so that as an end result
        </div>
        <div :class="$style.part2_image">
          <img src="@/assets/imgs/women_cleaner2.png" />
        </div>
        <div v-for="i in list" :key="i.id">
          <div :class="$style.tip">
            <span>{{ i.number }}</span>
            {{ i.title }}<br />
          </div>
          <div :class="$style.tip_description">{{ i.description }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Branding',
  data: () => ({
    show: false,
    imags: [
      require('@/assets/imgs/women_cleaner3.png'),
      require('@/assets/imgs/women_cleaner.png'),
      require('@/assets/imgs/women_cleaner2.png'),
    ],

    list: [
      {
        number: '1',
        title: 'Recurring discounts',
        description:
          'Demonstrate branding to, consequently, think outside the box. Take customer abc.',
      },
      {
        number: '2',
        title: 'Innovative cleaning techniques',
        description:
          'Demonstrate branding to, consequently, think outside the box. Take customer abc.',
      },
      {
        number: '3',
        title: 'flexible opening hours',
        description:
          'Demonstrate branding to, consequently, think outside the box. Take customer abc.',
      },
    ],
  }),
  methods: {
    visibilityChanged(isVisible) {
      if (isVisible) {
        this.show = true
      }
    },
  },
}
</script>

<style lang="scss" module>
.branding_main {
  display: flex;
  margin-top: 10%;
}

.brands_box {
  width: 45%;
  margin: 0 auto;
  position: relative;
}

.images {
  width: 60%;
  position: relative;

  img {
    width: 100%;
    border-radius: 10px;
    position: absolute;
    transition: all 0.4s ease;
    opacity: 0;
    &.image_active {
      opacity: 1;
      transform: translateX(0px) !important;
      transform: translateY(0px) !important;
    }
  }
}
.fix_size {
  margin-left: 24%;
}

.brand_title {
  font-size: 30px;
  font-weight: 400;
}

.brand_description {
  margin: 10% 0 18%;
  font-weight: 100;
}

.part2_image {
  display: none;
  position: relative;
  margin: 0 auto 10%;
  width: 70%;
  &:before {
    padding-bottom: 90%;
    content: '';
    display: block;
  }
  img {
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    width: 100%;
  }
}

.tip {
  display: flex;
  span {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: #31ad61;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
    margin-right: 6%;
  }
}

.tip_description {
  font-weight: 100;
  margin-left: 13%;
  margin-bottom: 9%;
  line-height: 1.4;
}

@media (max-width: 700px) {
  .branding_main {
    flex-wrap: wrap;
  }

  .brands_box {
    width: 80%;
  }

  .images {
    display: none;
  }

  .part2_image {
    display: block;
  }

  .fix_size {
    margin: 0;
    text-align: center;
  }

  .brand_description {
    margin: 10% 0;
  }

  .brand_title {
    font-size: 25px;
  }

  .tip_description,
  .tip {
    text-align: left;
  }
}

@media (max-width: 450px) {
  .brand_title {
    font-size: 20px;
  }

  .brand_description {
    font-size: 14px;
  }
  .tip span {
    width: 25px;
    height: 25px;
  }

  .tip_description,
  .tip {
    font-size: 13px;
  }
}
</style>
