<template>
  <div class="list-box">
    <div class="list-item" v-for="(item, idx) in props.listData" :key="'list' + idx">
      <div class="list-cont">
        <div class="list-tit">
          {{ item.title }}
        </div>
        <div class="list-info">
          <div class="cont-writer">
            <div class="writer-img">
              <img :src="item.profileImg" alt="프로필 이미지">
            </div>
            <div class="writer-name">{{ item.profileName }}</div>
          </div>
          <div class="cont-date">
            {{ item.date }}
          </div>
        </div>
      </div>
      <div class="list-other">
        <div class="cont-view">
          <div class="view-count">{{ item.viewCount }}</div>
          <div>조회수</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang='ts'>
  defineComponent({
    name: 'ListCont'
  })

  export type list = {
    title: string,
    profileImg: string,
    profileName: string,
    date: string,
    viewCount: number
  }

  const props = defineProps({
    listData:Array<list>
  })
</script>