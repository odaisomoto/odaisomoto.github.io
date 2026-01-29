---
title: 'Fery Prasetia'
date: 2025-09-25T16:58:51+03:00
tags: ['post']
image: 'index.png'
draft: true
---

Fery Prasetia - Resume & Portfolios

## Embedding Google Drive Videos

You can easily embed videos from Google Drive using the custom shortcode:

### How to Get Your Google Drive Video ID

1. Open your video in Google Drive
2. Click the three dots menu (⋮) and select "Share"
3. Set sharing to "Anyone with the link"
4. Copy the link - it will look like: `https://drive.google.com/file/d/YOUR_FILE_ID/view`
5. Extract the `YOUR_FILE_ID` part

### Usage Examples

**Basic usage with default sizing:**

```
{{</* gdrive-video id="YOUR_FILE_ID" */>}}
```

**Custom width and height:**

```
{{</* gdrive-video id="YOUR_FILE_ID" width="100%" height="600" */>}}
```

**Example (replace with your actual video ID):**

{{< gdrive-video id="1a2b3c4d5e6f7g8h9i0j" >}}
