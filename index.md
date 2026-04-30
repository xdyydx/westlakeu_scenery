---
layout: default
title: 我的短镜头库
---

<!-- 全屏蓝色标题栏（前后必须有空行） -->

<div class="page-header">
  <h1>🎬 我的短镜头库</h1>
</div>

<!-- 居中内容容器（前后必须有空行） -->

<div class="content-container">
  <table class="video-gallery">
    <thead>
      <tr>
        <th width="45%">视频预览</th>
        <th width="55%">内容描述</th>
      </tr>
    </thead>
    <tbody>
      {% for video in site.data.videos %}
      <tr>
        <td class="preview-cell">
          <video controls preload="metadata" width="100%">
            <!-- 预览用 Jsdelivr 加速 -->
            <source src="https://cdn.jsdelivr.net/gh/{{ site.cdn_username }}/{{ site.cdn_repo }}@{{ site.cdn_branch }}/videos/{{ video.filename }}" type="video/mp4">
            浏览器不支持视频播放
          </video>
        </td>
        <td class="desc-cell">{{ video.description }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>