<script setup>
</script>

<template>
<div class="Box">
  <div class="Header">
    <n-input size="large" round placeholder="Search artist, title, album" >
      <template #prefix>
        <img src="./../assets/images/search-normal.svg" alt="">
      </template>
    </n-input>
    <div class="avatar">
      <n-avatar
          round
          :size="46"
          src="https://07akioni.oss-cn-beijing.aliyuncs.com/07akioni.jpeg"
      />
    </div>
  </div>
  <div class="Body">
    <div class="Bar1">
      <h1>Recommended</h1>
      <div class="card">
          <div class="cover">
            <img src="https://07akioni.oss-cn-beijing.aliyuncs.com/07akioni.jpeg" alt="">
            <span>
              <img src="./../assets/images/play.svg" alt="">
            </span>
          </div>
        <div class="desc">
          <h2>Jiwa yang Bersedih</h2>
          <p>Ghea Indrawati</p>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<style scoped lang="scss">
.Box{
  flex: 1;
  padding: 32px;
}
.Header{
  display: flex;
  align-items: center;
  gap: 35px;
  &>div:nth-child(1){
    padding: 4px 12px;
    border-radius: 12px;
    border: 1px solid #e6e6e6;
    &>div:nth-child(1){
      margin: 0;
      padding: 0;
    }
  }
  &>div:nth-child(1):hover{
    border: 1px solid  #8568F5;
  }
  .avatar{
    padding: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 100px;
    background: linear-gradient(90deg, #3DC3C0 -15.19%, #8568F5 111.92%);
  }
}
.Body{
  display: flex;
  padding: 24px 0;
  h1{
    color: #121212;
    font-size: 18px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
  }
  .card{
    padding: 10px;
    display: flex;
    flex-direction: column;
    gap: 20px;
    .cover{
      position: relative;
      &>img{
        width: 170px;
        height: 170px;
        object-fit: cover;
        border-radius: 12px;
      }
      span{
        bottom: 20px;
        right: 10px;
        width: 36px;
        height: 36px;
        display: flex;
        flex: 1;
        align-items: center;
        justify-content: center;
        z-index: 100;
        position: absolute;
        border-radius: 100px;
        background: rgba(18, 18, 18, 0.50);
      }
    }
    .desc{
      h2{
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 1;
        align-self: stretch;overflow: hidden;
        color: #121212;
        text-overflow: ellipsis;
        font-size: 16px;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
      }
      p{
        color: #6B6B6B;
        font-size: 14px;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
      }
    }
  }
}
</style>