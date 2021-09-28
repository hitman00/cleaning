<template>
  <div :class="$style.testimonials_main">
    <div :class="$style.max_size">
      <div :class="$style.testimonials_tag">TESTIMONIALS</div>
      <div :class="$style.testimonials_title">Our happy clients</div>
      <div :class="$style.boxs">
        <div
          v-for="(i, id) in list"
          :key="id"
          v-observe-visibility="{
            callback: (e) => visibilityChanged(e, id),
            throttle: 500 + id + 1,
          }"
          :class="[$style.comment_box, i.show ? $style.active : '']"
        >
          <div :class="$style.stars">
            <Stars :full="i.star" />
          </div>
          <div :class="$style.comment">{{ i.comment }}</div>
          <div :class="$style.profile">
            <div :class="$style.profile_image">
              <img :src="i.img" />
            </div>
            <div :class="$style.name">
              {{ i.name }} <span>Happy Client</span>
            </div>
          </div>
        </div>
      </div>
      <div :class="$style.avrage_star">
        4.7* out of 5 stars frpm 123 reviews
      </div>
    </div>
  </div>
</template>

<script>
import Stars from './Stars/Stars.vue'
export default {
  name: 'Testimonials',
  components: {
    Stars,
  },
  data() {
    return {
      list: [
        {
          star: 5,
          comment:
            '"Lorem ipsum dolor sit amet consect adipisicing elit. Voluptates, aut natus suscipit iusto, ab quas, quidem architecto autem ea quod neque vitae. Odio aliquam sequi voluptatem eos suscipit obcaecati mollitia?"',
          name: 'Bill Campbell',
          img: require('@/assets/imgs/avatar.png'),
          show: false,
        },
        {
          star: 4,
          comment:
            '"Lorem ipsum dolor sit amet consect adipisicing elit. Voluptates, aut natus suscipit iusto, ab quas, quidem architecto autem ea quod neque vitae. Odio aliquam sequi voluptatem eos suscipit obcaecati mollitia?"',
          name: 'Sam Hunter',
          img: require('@/assets/imgs/avatar.png'),
          show: false,
        },
        {
          star: 5,
          comment:
            '"Lorem ipsum dolor sit amet consect adipisicing elit. Voluptates, aut natus suscipit iusto, ab quas, quidem architecto autem ea quod neque vitae. Odio aliquam sequi voluptatem eos suscipit obcaecati mollitia?"',
          name: 'Tommy Williams',
          img: require('@/assets/imgs/avatar.png'),
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
    },
  },
}
</script>

<style lang="scss" module>
.testimonials_main {
  background: #eceef0;
}

.max_size {
  max-width: 1230px;
  margin: 0 auto;
  padding-top: 8%;
}

.testimonials_tag {
  margin: 0% auto 2%;
  border: 1px solid #f2faf6;
  background: #eaf7ee;
  color: #5da67b;
  max-width: max-content;
  padding: 1%;
  border-radius: 4px;
}

.testimonials_title {
  font-size: 40px;
  font-weight: 400;
  text-align: center;
  margin: 0 16% 8%;
}
.boxs {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.comment_box {
  position: relative;
  width: 30%;
  background: #fff;
  border-radius: 5px;
  box-shadow: 1px 3px 5px #d0d0d0;
  padding: 3.2%;
  opacity: 0;
  transition: all 0.3s ease;
  transition-delay: 0.5s;
  &.active {
    opacity: 1;
  }
}
.stars {
  width: 33%;
  position: absolute;

  img {
    display: block;
    width: 100%;
  }
}

.comment {
  margin-top: 12%;
  margin-bottom: 22%;
  line-height: 1.6;
}

.profile {
  display: flex;
}

.profile_image {
  position: relative;
  width: 16%;
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

.name {
  margin-left: 6%;
  span {
    font-weight: 100;
    display: block;
  }
}

.avrage_star {
  margin-top: 3.5%;
  color: #31ad61;
  text-align: center;
  padding-bottom: 8.2%;
}

@media (max-width: 700px) {
  .testimonials_title {
    font-size: 30px;
  }

  .boxs {
    flex-direction: column;
  }

  .comment_box {
    width: 70%;
    margin-bottom: 3%;
  }
}

@media (max-width: 450px) {
  .testimonials_tag,
  .comment_box {
    font-size: 12px;
  }

  .testimonials_title {
    font-size: 18px;
  }

  .avrage_star {
    font-size: 14px;
  }
}
</style>
