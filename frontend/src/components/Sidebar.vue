<script setup>
import MMenu from "./MMenu.vue";
import {ref} from "vue";

let SelectMenu = ref("Home")
const Menu = ref(
    [
      {
        Title:"Discover",
        content:[
          {
            Title: "Home",
            IconPath: "src/assets/images/home-2.svg",
            Check: true
          },
          {
            Title: "Artist",
            IconPath: "src/assets/images/microphone.svg",
            Check: false
          },
          {
            Title: "Album",
            IconPath: "src/assets/images/music-library-2.svg",
            Check: false
          },
          {
            Title: "Podcast",
            IconPath: "src/assets/images/home-2.svg",
            Check: false
          },
          {
            Title: "Audio Book",
            IconPath: "src/assets/images/home-2.svg",
            Check: false
          }]
      },
      {
        Title:"Library",
        content:[
          {
            Title: "Recent",
            IconPath: "src/assets/images/home-2.svg",
            Check: false
          },
          {
            Title: "Favourit",
            IconPath: "src/assets/images/microphone.svg",
            Check: false
          },
          {
            Title: "Playlist",
            IconPath: "src/assets/images/music-library-2.svg",
            Check: false
          }]
      },
      {
        Title:"More",
        content:[
          {
            Title: "Setting",
            IconPath: "src/assets/images/home-2.svg",
            Check: false
          },
          {
            Title: "Account",
            IconPath: "src/assets/images/microphone.svg",
            Check: false
          },
          {
            Title: "Logout",
            IconPath: "src/assets/images/music-library-2.svg",
            Check: false
          }]
      }
    ]
  )

function MMenuClick(Index, Index2) {
  SelectMenu.value=Menu.value[Index].content[Index2].Title
  //遍历
  for (let i = 0; i < Menu.value.length; i++) {
    for (let j = 0; j < Menu.value[i].content.length; j++) {
      Menu.value[i].content[j].Check=false
    }
  }
  Menu.value[Index].content[Index2].Check=true
}

</script>

<template>
  <div id="Box">
    <!--  logo-->
    <div id="Logo">
      <img alt="" src="./../assets/images/logo.svg"/>
      <p>Musiverse</p>
    </div>
    <div class="MenuContent">
      <div v-for="(items,index) in Menu" :key="index" class="MenuItem">
        <p class="MenuTitle">{{items.Title}}</p>
        <div>
          <div v-for="(item,index2) in items.content" :key="index2" >
            <MMenu :IconPath="item.IconPath" :Switch="item.Check" :Title="item.Title" :item
                   @click="MMenuClick(index,index2)"></MMenu>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#Box {
  display: flex;
  flex-direction: column;
  width: 270px;
  padding: 32px 24px;
  align-items: flex-start;
  gap: 32px;
  box-shadow: 0 4px 20px 0 rgba(0, 0, 0, 0.12);
}

#Logo {
  display: flex;
  height: 44px;
  padding: 4px 0 4px 5px;
  justify-content: flex-end;
  align-items: center;
  gap: 9px;

  img {
    width: 26px;
    height: 36px;
  }

  p {
    font-size: 24px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
    letter-spacing: 2px;
    background: linear-gradient(90deg, #46BBC7 3.26%, #4488D8 56.45%, #8768F2 97.83%);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
}


.MenuContent {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 100%;
  .MenuItem{
    display: flex;
    flex-direction: column;
    gap: 17px;
    &>div{
      display: flex;
      flex-direction: column;
      gap: 2px;
    }
  }
  .MenuTitle {
    color: #3C3E43;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
  }
}

</style>