# Readme: weo

**watch episode of:**
`weo` is a very simple video-podcast-script to watch the last episode of a RSS-feed with video-content or everything that is supported by the youtube-dl backend of *`mpv`*.

*New (Sep 2019): The current version of "weo" supports youtube-channels. Player needs to be "mpv", see 'Configuration'.*


## Dependencies

Following Python3-libs need to be installed on your system:

- feedparser


## Install

- just copy "weo" to a folder in your `$PATH`.


## Configuration

- to change the default player from "mpv" to "mplayer", edit "`~/.weorc`":

```.sh
player=mplayer
```

## Usage

- edit (or create if not already done) "`~/.weofeeds`" with your favourite editor; this is the format:

```.json
{
    "feed": {
        "url": "https://feed.tld/rss",
        "match": 0,
        "match_type": "d"
    },
    "ytchannel": {
        "url": "https://youtube.com/user/channelName/videos",
        "url_type": "yt"
    }
}
```

- **`match_type`:** any value of `"d"` (day), `"w"` (week) or `"m"` (month).
- **`match`:** if `0` the current day, week or month (match_type) needs to match, otherwise the last days, weeks or months are valid. If the last eposide is not in that time frame, "weo" will ask
- **`url_type`** needs to be `"yt"` for Youtube-links.

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

