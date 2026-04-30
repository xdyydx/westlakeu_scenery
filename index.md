---
layout: default
title: 我的短镜头库
---

<!-- 全屏蓝色标题栏 -->
<div class="page-header">
  <h1>🎬 我的短镜头库</h1>
</div>

<!-- 居中内容容器 -->
<div class="content-container">
  <!-- 视频列表表格 -->
  <table class="video-gallery">
    <thead>
      <tr>
        <th width="35%">视频预览</th>
        <th width="45%">内容描述</th>
        <th width="20%">下载操作</th>
      </tr>
    </thead>
    <tbody>
      {% for video in site.data.videos %}
      <tr>
        <td class="preview-cell">
          <video controls preload="metadata" width="100%">
            <source src="https://cdn.jsdelivr.net/gh/{{ site.cdn_username }}/{{ site.cdn_repo }}@{{ site.cdn_branch }}/videos/{{ video.filename }}" type="video/mp4">
            浏览器不支持视频播放
          </video>
        </td>
        <td class="desc-cell">{{ video.description }}</td>
        <td class="download-cell">
          <a 
            href="https://cdn.jsdelivr.net/gh/{{ site.cdn_username }}/{{ site.cdn_repo }}@{{ site.cdn_branch }}/videos/{{ video.filename }}" 
            class="download-btn"
            download="{{ video.filename }}"
            target="_blank"
          >
            ⬇️ 下载视频
          </a>
        </td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>