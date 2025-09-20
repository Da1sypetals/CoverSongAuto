# 翻唱视频自动生成

仅为最小化自我定制功能使用，功能少，但定制化程度高。

# 视频制作流程

代码都放在：`~\CoverSongAuto\`

## 歌词
- `lrc/` 和 `video/` 下分别有 `index.html`，分别是歌词打时间戳转lrc工具和视频生成工具。
### 步骤
1. 把歌词复制到 lrc generator, 自己打一遍，生成 lrc 格式（实测比去音乐网站爬取效率高）
2. lrc 格式歌词、封面图、其他元信息，复制到视频生成页面中，开启视频，录屏。
3. 用以下命令把视频从 mkv 格式转为 mp4 格式。ffmpeg 会根据extension自动猜测文件格式，所以extension一定要写对。
```
ffmpeg -i <source_video.mkv> -c copy <destination_video.mp4>
```

## 封面
用即梦AI https://jimeng.jianying.com/ai-tool/home ，把YOUR_SONG_TITLE换成歌曲名，然后用这一段prompt生成多个图。


```
十分潦草飘逸的草书，书法字，内容：“YOUR_SONG_TITLE”，单行，每个文字之间轻微上下起伏排版，白底黑字
```

然后再用图片参考，用prompt `把这副书法放到 <xx环境> 里` ，即可生成带背景的书法图

## 音频
把全民k歌的歌曲链接复制到浏览器里，F12 检查元素，在html里面搜 `.m4a`，找到音频的链接下载下来。

## 成品

视频掐头去尾，对齐音频。