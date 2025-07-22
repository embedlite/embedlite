# EmbedLite

A drop-in, open-source replacement for YouTube embed iframes. Lightning fast, SEO-optimized, and privacy-friendly.

## Why EmbedLite?

YouTube’s embed iframe is a nightmare. It loads a bunch of scripts, tracking, and assets (even if the user never hits play). This hurts load times, SEO, and overall user experience, especially on mobile or pages with multiple videos.

EmbedLite works by replacing the iframe with a lightweight placeholder that only loads the real YouTube player when clicked. Here's how it works:

```diff
-- <iframe src="https://youtube.com/embed/..."
++ <iframe src="https://embedlite.com/embed/..."
```

Making your website faster, with better performance and improved privacy.

## Usage

Replace the YouTube domain in your iframe embed:

```diff
-- <iframe src="https://youtube.com/embed/..."
++ <iframe src="https://embedlite.com/embed/..."
```

Then you get something similar to https://github.com/paulirish/lite-youtube-embed or https://github.com/justinribeiro/lite-youtube.

Prefer full control? You can deploy your own version of EmbedLite using:

- [Cloudflare Pages](https://pages.cloudflare.com/)
- [Vercel](https://vercel.com/)
- [Netlify](https://www.netlify.com/)
- Any static file host

## Parameters

| Name         | Description |
|--------------|-------------|
| `VIDEO_ID`   | YouTube video ID (required) |
| `title`      | Custom video title to display (overrides default YouTube title) |
| `autoplay`   | Set to `true` or `1` to auto-play on click |
| *other params* | All other query params are passed directly to the YouTube iframe (e.g. `controls`, `mute`, `start`, `end`, `loop`, etc.) |

## Examples

 Basic embed (what you get from the YouTube embed code):

```diff
<iframe width="560" height="315" src="https://www.youtube.com/embed/jNQXAC9IVRw" title="Me at the zoo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.embedlite.com/embed/jNQXAC9IVRw" title="Me at the zoo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

With YouTube parameters:

```
https://embedlite.com/embed/dQw4w9WgXcQ?controls=0&mute=1&start=30&end=120
```

With custom title:

```
https://embedlite.com/embed/dQw4w9WgXcQ?autoplay=true&title=Rick%20Astley
```

## Disclaimer

EmbedLite is not affiliated with YouTube or Google in any way. This project uses the official YouTube embed player and complies with [YouTube's Terms of Service](https://www.youtube.com/t/terms) by loading the standard YouTube iframe only after user interaction.
