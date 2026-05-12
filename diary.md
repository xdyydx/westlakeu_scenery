---
layout: default
title: 日志
---

<!-- 全屏蓝色标题栏（和首页完全一致） -->

<div class="page-header">
  <h1>📝 日志（碎碎念）</h1>
</div>

<!-- 日志内容容器（和首页容器样式一致） -->

<div class="content-container">
  <div class="diary-list">
    {% for item in site.data.diary %}
    <div class="diary-item">
      <!-- 左上角时间 -->
      <div class="diary-date">{{ item.date }}</div>
      
      <!-- 蓝色小圆+绿色分割线 -->
      <div class="diary-divider">
        <span class="blue-dot"></span>
        <span class="green-line"></span>
      </div>
      
      <!-- 日志内容（自动换行，支持Markdown） -->
      <div class="diary-content">
        {{ item.content | markdownify }}
      </div>
    </div>
    {% endfor %}
  </div>
</div>