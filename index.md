---
# index.md
layout: default
title: 视频列表
---

# 🎬 我的短镜头库

<!-- 无框表格布局 -->
<table class="video-gallery">
    <thead>
        <tr>
            <th>预览</th>
            <th>描述</th>
            <th>下载</th>
        </tr>
    </thead>
    <tbody>
        <!-- Liquid 循环开始 -->
        {% for video in site.data.videos %}
        <tr>
            <td class="preview-cell">
                <video width="280" height="160" controls preload="metadata">
                    <source src="https://cdn.jsdelivr.net/gh/{{ site.cdn_username }}/{{ site.cdn_repo }}@{{ site.cdn_branch }}/videos/{{ video.filename }}" type="video/mp4">
                    浏览器不支持视频播放
                </video>
            </td>
            <td class="desc-cell">{{ video.description }}</td>
            <td class="download-cell">
                <a href="https://cdn.jsdelivr.net/gh/{{ site.cdn_username }}/{{ site.cdn_repo }}@{{ site.cdn_branch }}/videos/{{ video.filename }}" target="_blank" class="download-btn">⬇️ 下载视频</a>
            </td>
        </tr>
        {% endfor %}
    </tbody>
</table>