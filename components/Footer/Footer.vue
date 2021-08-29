<template>
  <div :class="$style.footer_main">
    <div :class="$style.max_size">
      <div :class="$style.share_link">
        <div :class="$style.logo">
          <img src="@/assets/imgs/logo.png" />
        </div>
        <div :class="$style.description">
          Professional cleaning services in Prague . Another text line here.
        </div>
        <div :class="$style.social_networks">
          <div v-for="(i, id) in list" :key="id" :class="$style.box_image">
            <img :src="i" />
          </div>
        </div>
        <div :class="$style.copy_right">@ 2020 Copyright Magnoia.</div>
      </div>
      <div :class="$style.context">
        <div
          v-for="(item, id) in links"
          :key="id"
          :class="[$style.context_box, id == 2 ? $style.remove : '']"
        >
          <div :class="$style.context_title">{{ item.title }}</div>
          <ul>
            <li v-for="page in item.pages" :key="page.id" v-html="page"></li>
          </ul>
        </div>
      </div>
    </div>
    <div :class="$style.company_creat">
      @ 2020 Clearing company Prague | Cleaning Prague | GDPR | GDPR and cookie
      consent
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      list: [
        require('@/assets/imgs/twiter.png'),
        require('@/assets/imgs/facebook.png'),
        require('@/assets/imgs/linked.png'),
      ],
      links: [
        {
          title: 'Quick Links',
          pages: [
            'Pricelist of services',
            'About Magnolia',
            'Cleaning in prague',
            'Home Cleaning',
            'Office cleaning',
            'Book the cleaning online',
            'Our Blog',
          ],
        },
        {
          title: 'Cleaning Services',
          pages: [
            'General Home Cleaning',
            'Office cleaning',
            'Home Cleaning',
            'Cleaning',
            'About Magnolia',
            'Cleaning in prague',
          ],
        },
        {
          title: 'Contact Us',
          pages: [
            'Opering hours:',
            'Cleaning 7 days per week',
            '8:00 AM - 8:00 PM',
            '<a style="margin-top: 21%;" href="mailto:info@hitman00.com">info@hitman00.com</a>',
            '<a href="tel:+123 456 789 012">+123 456 789 012</a>',
          ],
        },
      ],
    }
  },
}
</script>

<style lang="scss" module>
.footer_main {
  width: 100%;
  background: #161616;
  color: #fff;
  padding-bottom: 10%;
  position: relative;
}

.max_size {
  max-width: 1230px;
  margin: 0 auto;
  display: flex;
  padding: 0 2%;
}

.share_link {
  width: 40%;
  font-weight: 100;
}

.context {
  width: 60%;
  display: flex;
  justify-content: space-between;
}

.context_box {
  ul li {
    font-weight: 100;
    line-height: 2;
    opacity: 0.6;
    cursor: pointer;
    transition: all 0.3s ease;
    &:hover {
      opacity: 0.9;
    }
  }
}

.context_title {
  margin-top: 42%;
  margin-bottom: 23%;
}
.remove {
  ul li {
    cursor: text;
    &:hover {
      opacity: 0.6;
    }
    a {
      display: block;
      color: #31ad61;
      cursor: pointer;
      transition: all 0.3s ease;
      &:hover {
        color: #5ce28f;
      }
    }
  }
}

.logo {
  position: relative;
  width: 15%;
  margin-top: 13%;
  margin-bottom: 8.5%;
  &:before {
    content: '';
    padding-bottom: 50%;
    display: block;
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

.description {
  margin-right: 44%;
  margin-bottom: 9%;
}

.social_networks {
  display: flex;
}

.box_image {
  width: 10.2%;
  border-radius: 50%;
  background: #31ac60;
  position: relative;
  margin-right: 2%;
  margin-bottom: 4%;

  &:before {
    padding-bottom: 100%;
    display: block;
    content: '';
  }
  img {
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    padding: 30% 28%;
    width: 100%;
  }
}

.company_creat {
  width: 100%;
  position: absolute;
  bottom: 0;
  text-align: center;
  background: #262626;
  padding: 2%;
  opacity: 0.8;
  font-weight: 100;
}

@media (max-width: 700px) {
  .max_size {
    flex-direction: column-reverse;
  }

  .context {
    justify-content: space-evenly;
    width: 100%;
  }

  .share_link {
    width: 80%;
    margin: 0 auto;
    text-align: center;
  }

  .logo {
    margin-left: auto;
    margin-right: auto;
  }

  .description {
    margin-right: 0;
  }

  .social_networks {
    justify-content: center;
  }

  .copy_right {
    margin-bottom: 5%;
  }

  .company_creat {
    font-size: 10px;
  }
}

@media (max-width: 600px) {
  .context {
    width: 100%;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .context_title {
    margin: 9% 0;
    font-size: 20px;
  }
}

@media (max-width: 450px) {
  .description,
  .copy_right {
    font-size: 14px;
  }
}
</style>
