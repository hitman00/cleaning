<template>
  <div :class="$style.company_main">
    <div :class="$style.tag">MAGNOLIA</div>
    <div :class="$style.title">
      Our cleaning company offers quality cleaning services in prague
    </div>
    <div :class="$style.services_slid">
      <div
        v-for="(item, id) in list"
        :key="id"
        v-observe-visibility="{
          callback: (e) => visibilityChanged(e, id),
          throttle: 500 * id + 1,
        }"
      >
        <div :class="[$style.icon, item.show ? $style.active : '']">
          <img :src="item.img" />
        </div>
        <div :class="[$style.show_box, item.show ? $style.active_text : '']">
          <div :class="$style.services_title">
            {{ item.title }}
          </div>
          <div :class="$style.services_description">{{ item.description }}</div>
        </div>
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
  data() {
    return {
      list: [
        {
          img: require('@/assets/imgs/icon1.png'),
          title: 'Our cleaning company cleans everything and everywhere',
          description:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sed enim ea ab praesentium veniam dolorum',
          show: false,
        },
        {
          img: require('@/assets/imgs/flower.png'),
          title: 'Magnolia will relieve you of your worries',
          description:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sed enim ea ab praesentium veniam dolorum',
          show: false,
        },
        {
          img: require('@/assets/imgs/icon2.png'),
          title: 'One-time and regular home cleaning',
          description:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sed enim ea ab praesentium veniam dolorum',
          show: false,
        },
      ],
    }
  },

  methods: {
    visibilityChanged(isVisible, id) {
      if (isVisible) {
        this.list[id].show = true
      }
      // callback: (e) => visibilityChanged(e, id),
      // const callback=function (e,id) {
      // return visibilityChanged(e,id)
    },
  },
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
  opacity: 0;
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
  &.active {
    opacity: 1;
    animation: example 0.3s linear;
  }
}

@keyframes example {
  0% {
    transform: scale(0);
    opacity: 1;
  }
  50% {
    transform: scale(1.3);
    opacity: 1;
  }
  100% {
    transform: scale(1);
    opacity: 1;
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

.show_box {
  opacity: 0;
  &.active_text {
    opacity: 1;
    animation: text 0.5s linear;
  }
}
@keyframes text {
  0% {
    opacity: 0;
    transform: translateY(100px);
  }
  100% {
    opacity: 1;
    transform: translateY(0px);
  }
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

@media (max-width: 450px) {
  .tag,
  .services_description {
    font-size: 12px;
  }

  .title {
    font-size: 18px;
  }

  .services_title {
    font-size: 15px;
  }
}
</style>
