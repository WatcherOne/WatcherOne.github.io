---
title: '404 - 好巧，竟然在这里遇到您！'
permalink: /404.html
hide: true
comment: false
---

#### 这是一个不存在的页面 Todo

- 5秒后返回首页

<script>
let countTime = 5;

function count() {
  document.getElementById('timeout').textContent = countTime;
  countTime -= 1;
  if(countTime === 0){
    location.href = 'Richard Zhu';
  }
  setTimeout(() => {
    count();
  }, 1000);
}

count();
</script>
