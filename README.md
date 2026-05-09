# HLS Compatibility Tests

> Test native browser HLS compatibility via streams synced from [the HLS.js demo](https://hlsjs.video-dev.org/demo/)

Native HLS compatibility varies across browsers. Compatibility problems can show up with eg. streams using gzip-encoded `.m3u8` playlists ([Chromium issue 507987650](https://issues.chromium.org/issues/507987650)), audio-only streams, alternate audio, subtitles, captions, and live or low-latency streams.

## Local usage

Open `index.html` in a browser, or serve the directory with any static server:

```sh
python3 -m http.server 8000
```

Then visit `http://localhost:8000/`.

Pass a stream directly with `?src=`:

```text
http://localhost:8000/?src=https%3A%2F%2Ftest-streams.mux.dev%2Fx36xhzz%2Fx36xhzz.m3u8
```

## Stream definitions

The stream list is based on HLS.js `tests/test-streams.js`:

https://github.com/video-dev/hls.js/blob/master/tests/test-streams.js

Run the manual [`Sync HLS.js stream definitions`](.github/workflows/sync-streams.yml) GitHub Actions workflow to refresh the generated stream records from upstream.
