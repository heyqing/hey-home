<template>
  <div>
    <div class="desc">
      <h1>简单说明</h1>
      <span style="font-size: larger;margin: 5px;">本页面主要用来做网页导航的,以下图片皆可通过点击前往相应网站</span><br>
      <span style="font-size: small;margin: 25px 0px 30px 6px;color: grey;">由于人力、财力等等因素影响此页面简陋做之。</span>
    </div>
    <div class="main">
      <div class="card" v-for="item in data" :key="item.img">
        <a :href="item.href" target="_blank" rel="noopener noreferrer">
          <img :src="item.img" :alt="item.title">
          <div class="overlay">
            <h2>{{ item.title }}</h2>
            <p>{{ item.desc }}</p>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  setup() {
    const data = ref([
      {
        img: '/chh.png',
        title: '刺槐花',
        desc: '刺槐花官网 | 点击可前往',
        href: 'http://heyqing.top',
      },
      {
        img: '/bg.jpg',
        title: '初晴',
        desc: '个人博客网站 | 点击可前往',
        href: 'http://heyqing.top/blog/',
      },
      {
        img: '/sp.jpg',
        title: '何以晴',
        desc: '作者简介 | 点击可前往',
        href: 'http://heyqing.top/my/',
      },
      {
        img: '/github.png',
        title: 'Github',
        desc: '作者Github地址 | 点击可前往',
        href: 'https://github.com/heyqing',
      },
      {
        img: '/gitee.jpg',
        title: 'Gitee',
        desc: '作者Gitee地址 | 点击可前往',
        href: 'https://gitee.com/heyqing',
      },
      {
        img: '/xt.jpg',
        title: '稀土掘金',
        desc: '作者稀土掘金地址 | 点击可前往',
        href: 'https://juejin.cn/user/2056511791331820',
      },
      {
        img: '/csdn.png',
        title: 'CSDN',
        desc: '作者CSDN地址 | 点击可前往',
        href: 'https://blog.csdn.net/heyiqingsong',
      },
      {
        img: '/twitter.png',
        title: '推特',
        desc: '作者推特地址 | 点击可前往',
        href: 'https://x.com/heyqings',
      }
    ]);
    return { data };
  },
};
</script>


<style scoped>
.desc {
  height: 35vh;
  margin: 12px 0px 10px 12px;
  padding: 10px;
  border-radius: 16px;
  color: white;
  text-align: center;
  background: radial-gradient(circle, #000000, #3b076b, #680a4a, #c2790c, #b10b0b);
  position: relative;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(255, 255, 255, 0.2);
  animation: background-move 10s infinite alternate ease-in-out;
}

/* 动态背景动画 */
@keyframes background-move {
  0% {
    background: radial-gradient(circle, #000000, #1a0033, #4b0033, #660022, #990000);
  }

  25% {
    background: radial-gradient(circle, #a3a51e, #bd2665, #5a8f29, #197a5a, #254b85, );
  }

  50% {
    background: radial-gradient(circle, #1d887f, #7661d3, #553377, #611561, #99097a85);
  }

  75% {
    background: radial-gradient(circle, #940c27, #ac3351, #553b6e, #32588d, #011c52);
  }

  100% {
    background: radial-gradient(circle, #160a30, #660e77, #961c1c, #6d2f2f, #d36906);
  }
}

@keyframes twinkle {

  0%,
  100% {
    opacity: 0.4;
    transform: scale(0.8);
  }

  50% {
    opacity: 1;
    transform: scale(1.5);
  }
}



.main {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  padding: 10px;
}

.card {
  width: 96vw;
  height: 88vh;
  margin-top: 5px;
  border-radius: 16px;
  overflow: hidden;
  position: relative;
  /* 添加相对定位 */
}

.card img {
  width: 100%;
  height: 100%;
  display: block;
  border-radius: 16px;
}

.overlay {
  position: absolute;
  /* 绝对定位 */
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  /* 半透明背景 */
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  opacity: 0;
  /* 初始透明度为0 */
  transition: opacity 0.3s;
  /* 过渡效果 */
}

.card:hover .overlay {
  opacity: 1;
  /* 悬浮时显示 */
}
</style>