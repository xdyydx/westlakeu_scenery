---
layout: default
title: 我的短镜头视频库
---

<!-- 标题栏 -->
<header class="page-header">
  <h1>🎬 我的短镜头库</h1>
</header>

<!-- 视频表格 -->
<table class="video-gallery">
  <thead>
    <tr>
      <th>视频预览</th>
      <th>内容描述</th>
      <th>下载</th>
    </tr>
  </thead>
  <tbody>
    {% for video in site.data.videos %}
    <tr>
      <td class="preview-cell">
        <video controls preload="metadata">
          <source src="https://cdn.jsdelivr.net/gh/{{ site.cdn_username }}/{{ site.cdn_repo }}@{{ site.cdn_branch }}/videos/{{ video.filename }}" type="video/mp4">
          浏览器不支持视频播放
        </video>
      </td>
      <td class="desc-cell">{{ video.description }}</td>
      <td class="download-cell">
        <!-- ✅ 关键：添加 download 属性，实现自动下载，不跳转预览 -->
        <a 
          href="https://cdn.jsdelivr.net/gh/{{ site.cdn_username }}/{{ site.cdn_repo }}@{{ site.cdn_branch }}/videos/{{ video.filename }}" 
          target="_blank"
          class="download-btn"
          download
        >
          ⬇️ 下载视频
        </a>
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>