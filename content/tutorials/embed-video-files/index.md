---
aliases: ["/blog/embed-video-files/"]
title: "Embed Video Files"
date: "2022-04-26T01:16:18+02:00"
toc: false
---

Use the `video` shortcode (`layouts/_shortcodes/video.html`) to embed video files from
[Hugo Page Resources](https://gohugo.io/content-management/page-resources/).

{{< video src="my-video" autoplay="true" controls="false" loop="true" >}}

<!--more-->

With a page bundle looking like the following:

```text
embed-video-files/
|-- index.md
|-- my-video.jpg
|-- my-video.mp4
|-- my-video.webm
```

You can embed `my-video` like this:

```markdown
{{</* video src="my-video" autoplay="true" controls="false" loop="true" */>}}
```

The shortcode looks for `my-video.webm` and `my-video.mp4` and adds a `<source>` element for each
one it finds. `my-video.jpg`, if present, is used as the poster (thumbnail).

| Attribute  | Default | Notes                                       |
| ---------- | ------- | ------------------------------------------- |
| `src`      |         | file name without extension                 |
| `autoplay` | `false` | autoplaying videos are also muted (browsers require it) |
| `controls` | `true`  |                                             |
| `loop`     | `false` |                                             |

[Learn more about the `<video>` attributes here.](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attributes)
