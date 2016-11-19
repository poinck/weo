# Readme: weo

**watch episode of:**
`weo` is a very simple video-podcast-script to watch the last episode of a RSS-feed with video-content in MP4-format.

*A future version of "weo" will support youtube-channels by extracting the url with `youtube-dl`*


## Dependencies

Following Python3-libs need to be installed on your system:

- feedparser


## Install

- just copy "weo" to a folder in your `$PATH`.


## Usage

- edit (or create if not already done) "`~/.weofeeds`" with your favourite editor; this is the format:

```.json
{
    "feed": {
        "url": "http://feed.tld/rss",
        "match": 0,
        "match_type": "d"
    }
}
```

- **`match_type`:** any value of `"d"` (day), `"w"` (week) or `"m"` (month).
- **`match`:** if `0` the current day, week or month (match_type) needs to match, otherwise the last days, weeks or months are valid. If the last eposide is not in that time frame, "weo" will ask

### Usage example

```.sh
$ weo -l
following feeds are configured in "~/.weofeeds":
  feed
$ weo feed
last episode of "Video-Feed in HD" is from 17.11.2016
play anyway? [y/N] y
playing ..
```

*A future version of "weo" will enable you adding podcast-feeds without editing the JSON-formatted feeds-file yourself*


## License

No license.

