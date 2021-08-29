<template>
  <div :class="$style.company_main">
    <div :class="$style.tag">MAGNOLIA</div>
    <div :class="$style.title">
      Our cleaning company offers quality cleaning services in prague
    </div>
    <div :class="$style.services_slid">
      <div v-for="(item, id) in list" :key="id">
        <div :class="$style.icon">
          <img :src="item.img" />
        </div>
        <div :class="$style.services_title">
          {{ item.title }}
        </div>
        <div :class="$style.services_description">{{ item.description }}</div>
      </div>
    </div>
    <div :class="$style.tag">Features</div>
    <div :class="$style.title">
      Our cleaning company offers quality cleaning services in prague
    </div>
    <Features />
    <Branding />
    <div :class="$style.tag">ABOUT US</div>
    <div :class="$style.title">
      Our cleaning company offers quality cleaning services in prague
    </div>
    <AboutUs />
  </div>
</template>

<script>
import Features from './Features/Features.vue'
import Branding from './Branding/Branding.vue'
import AboutUs from './AboutUs/AboutUs.vue'
export default {
  name: 'Company',
  components: {
    Features,
    Branding,
    AboutUs,
  },
  data: () => ({
    list: [
      {
        img: require('@/assets/imgs/icon1.png'),
        title: 'Our cleaning company cleans everything and everywhere',
        description:
          'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sed enim ea ab praesentium veniam dolorum',
      },
      {
        img: require('@/assets/imgs/flower.png'),
        title: 'Magnolia will relieve you of your worries',
        description:
          'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sed enim ea ab praesentium veniam dolorum',
      },
      {
        img: require('@/assets/imgs/icon2.png'),
        title: 'One-time and regular home cleaning',
        description:
          'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sed enim ea ab praesentium veniam dolorum',
      },
    ],
  }),
}
</script>

<style lang="scss" module>
.company_main {
  max-width: 1230px;
  margin: 0 auto;
}

.tag {
  margin: 10% auto 2%;
  border: 1px solid #f2faf6;
  background: #eaf7ee;
  color: #5da67b;
  max-width: max-content;
  padding: 1%;
  border-radius: 4px;
}

.title {
  font-size: 40px;
  font-weight: 400;
  text-align: center;
  margin: 0 16% 8%;
}

.services_slid {
  display: flex;
  text-align: center;
}

.icon {
  position: relative;
  width: 20%;
  background: #31ad61;
  border-radius: 50%;
  margin: 0 auto 7%;

  &:before {
    content: '';
    display: block;
    padding-bottom: 100%;
  }
  img {
    position: absolute;
    bottom: 0;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    padding: 32% 15%;
  }
}

.services_title {
  font-size: 23px;
  font-weight: 400;
  margin: 0 8%;
}
.services_description {
  font-weight: 100;
  margin: 7% 10%;
}

@media (max-width: 900px) {
  .title {
    font-size: 30px;
    margin: 0 10% 8%;
  }

  .services_title {
    font-size: 18px;
  }

  .services_description {
    font-size: 15px;
  }
}

@media (max-width: 700px) {
  .services_slid {
    flex-wrap: wrap;
    justify-content: center;
  }

  .services_description {
    margin: 3% 10% 6%;
  }

  .icon {
    margin-bottom: 4%;
  }
}
</style>
