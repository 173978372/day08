<template>
  <component :is="blockTypeMap[props.data.blockCode]" :data="translate" />
</template>

<script setup>
import { computed, defineProps } from 'vue'

import Menu from './Menu.vue'
import Banner from './Banner.vue'

const blockTypeMap = {
  HOMEPAGE_BANNER: Banner,
  HOMEPAGE_BLOCK_OLD_DRAGON_BALL: Menu,
  HOMEPAGE_BLOCK_PLAYLIST_RCMD: '',
  HOMEPAGE_BLOCK_STYLE_RCMD: '',
  HOMEPAGE_BLOCK_NEW_ALBUM_NEW_SONG: '',
  HOMEPAGE_BLOCK_HOT_TOPIC: '',
  HOMEPAGE_MUSIC_CALENDAR: '',
  HOMEPAGE_MUSIC_MLOG: '',
  HOMEPAGE_BLOCK_MGC_PLAYLIST: '',
  HOMEPAGE_BLOCK_OFFICIAL_PLAYLIST: '',
  HOMEPAGE_VOICELIST_RCMD: '',
  HOMEPAGE_PODCAST24: '',
  HOMEPAGE_BLOCK_YUNCUN_PRODUCED: '',
  HOMEPAGE_BLOCK_VIDEO_PLAYLIST: '',
  HOMEPAGE_BLOCK_NEW_HOT_COMMENT: '',
  HOMEPAGE_VOICEBOOK_RCMD: ''
}

const props = defineProps({
  data: {
    type: Object,
    required: true
  }
})

const translate = computed(() => {
  switch (props.data.blockCode) {
    case 'HOMEPAGE_BLOCK_OLD_DRAGON_BALL':
      return props.data.creatives[0].resources.map((item) => {
        return {
          name: item.uiElement.mainTitle.title,
          img: item.uiElement.image.imageUrl
        }
      })

    default:
      return []
  }
})
console.log(blockTypeMap[props.data.blockCode])
</script>
