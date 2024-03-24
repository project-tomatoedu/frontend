<template>
  <div class="lecture-card" v-for="(item, idx) in props.lectureData" :key="'lecture' + idx">
    <NuxtLink to="path" class="lecture-link">
      <span class="lecture-thumb">
        <img class="thumb-img" :src="item.thumbImg" alt="강의 이미지">
        <button type="button" class="like-btn">
          <span class="hidden">
            강의 좋아요
          </span>
        </button>
      </span>
      <span class="lecture-name">
        {{ item.name }}
      </span>
    </NuxtLink>
    <NuxtLink class="lecture-cate">
      {{ item.category }}
    </NuxtLink>
    <div class="lecture-info">
      <div class="lec-other">
        <span class="lec-level">
          {{ item.level }}
        </span>
        <span class="lec-like">
          {{ item.like }}
        </span>
        <span class="lec-rate">
          {{ item.rate }}
        </span>
      </div>
      <div class="lec-price">
        {{ item.price }}
      </div>
    </div>
  </div>
</template>

<script setup lang='ts'>
  defineComponent({
    name: 'LectureCard'
  })

  export type lecture = {
    thumbImg: string,
    name: string,
    category: string,
    level: string,
    like: number,
    rate: number,
    price: number | string
  }

  const props = defineProps({
    lectureData:Array<lecture>
  })
</script>