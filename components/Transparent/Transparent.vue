<template>
  <div :class="$style.transparent_main">
    <div :class="$style.max_size">
      <div :class="$style.title">Generate innovation but be transparent</div>
      <div :class="$style.description">
        Do you need a quality office cleaning or home cleaning once a week? Or
        just one proper general cleaning? whatever you need magnolia - Cleaning
        services will aadapt exactly to your needs.
      </div>
      <div :class="$style.btn">Get an Estimate</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Transparent',
}
</script>

<style lang="scss" module>
.transparent_main {
  width: 100%;
  position: relative;
  background: #31ad61;
  text-align: center;
  color: #fff;
  padding-bottom: 4%;
}

.max_size {
  max-width: 1230px;
  margin: 0 auto;
}

.title {
  font-size: 30px;
  padding-top: 70px;
}

.description {
  width: 74%;
  margin: 2.5% auto;
  line-height: 1.8;
  font-weight: 100;
}

.btn {
  background: #fff;
  border-radius: 5px;
  color: #31ad61;
  display: inline-block;
  margin: 0 auto;
  padding: 1%;
  cursor: pointer;
  transition: all 0.3s ease;
  &:hover {
    opacity: 0.8;
  }
}

@media (max-width: 700px) {
  .title {
    font-size: 25px;
  }

  .description {
    font-size: 14px;
  }
}

@media (max-width: 450px) {
  .title {
    font-size: 18px;
  }

  .description,
  .btn {
    font-size: 13px;
  }
}
</style>
