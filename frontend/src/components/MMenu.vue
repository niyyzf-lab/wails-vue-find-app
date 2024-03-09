<script setup>
const props=defineProps({
  Switch:Boolean,
  Title:String,
  IconPath:String,
})
</script>

<template>
  <div class="Box On" v-if="props.Switch">
    <img :src=props.IconPath alt=""/>
    <p>{{props.Title}}</p>
  </div>
  <div class="Box" v-else>
    <img :src=props.IconPath alt=""/>
    <p>{{props.Title}}</p>
  </div>
</template>

<style scoped lang="scss">
.Box{
  display: flex;
  padding: 20px 24px;
  border-radius: 12px;
  gap: 10px;
  cursor: pointer;
  &:hover{
    background: #ebebeb;
    img{
      width: 24px;
      height: 24px;
      overflow: hidden;
      filter: drop-shadow(#3a3a3a 100px 0);
      transform: translateX(-100px);
    }
    p{
      color: #3a3a3a;
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: normal;
    }
  }
  img{
    width: 24px;
    height: 24px;
    overflow: hidden;
    filter: drop-shadow(#999999 100px 0);
    transform: translateX(-100px);
  }
  p{
    color: #999;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
  }
}
.On{
  background: linear-gradient(90deg, #3DC3C0 -15.19%, #8568F5 111.92%);
  img{
    width: 24px;
    height: 24px;
    overflow: hidden;
    filter: drop-shadow(#FFF 100px 0);
    transform: translateX(-100px);
  }
  p{
    color: #FFF;
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
  }
  &:hover{
    background: linear-gradient(90deg, #2be3e0 -15.19%, #601df4 111.92%);
    p{
      color: #FFF;
      font-size: 16px;
      font-style: normal;
      font-weight: 600;
      line-height: normal;
    }
    img{
      width: 24px;
      height: 24px;
      overflow: hidden;
      filter: drop-shadow(#FFF 100px 0);
      transform: translateX(-100px);
    }
  }
}
</style>