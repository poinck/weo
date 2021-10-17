# Readme: weo

**watch episode of:**
`weo` is a very simple video-podcast-script to watch the last episode of a RSS-feed with video-content using *`mpv`*.

*New (2021): List episodes of a feed, configure custom names and url_templates if your local news provide cannot provide current RSS feeds. See 'Usage'.*

*Attention: Direct YT-Channel support is depricated now. Get RSS-Feed of YT-Channels instead.*


## Dependencies

Following Python3-libs need to be installed on your system:

- feedparser


## Install

- copy "weo" to a folder in your `$PATH` or create a symlink to it.


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
        "match_type": "d",
        "name": "Long feed name"
    },
    "feed2": {
        "url": "https://feed.tld/episode_${yyyymmdd}",
        "url_type": "template"
        "match": 0,
        "match_type": "d",
        "name": "Second daily feed"
    }
}
```

- **`url_type`:** if `"template"` the url must contain "`${yyyymmdd}`" in order to generate a virtual feed. Useful for sites without or not current RSS.
- **`match_type`:** any value of `"d"` (day), `"w"` (week) or `"m"` (month).
- **`match`:** if `0` the current day, week or month (match_type) needs to match, otherwise the last days, weeks or months are valid. If the last eposide is not in that time frame, "weo" will ask
- **`name`** is optional

### Usage examples

```.sh
$ weo -l
following feeds are configured in "~/.weofeeds":
  feed      Long feed name
  feed2     Second daily feed
$ weo feed
last episode (Videofeed in HD) of feed is from 2021-10-14
play anyway? [y/N] y
playing ..

# getting help
$ weo -h
usage: weo [-h] [-v] [-l] [-c] [FEED] [EPISODE]

weo-4: watch episode of

positional arguments:
  FEED           feed shortcut
  EPISODE        last episode number (default: 0, newest)

optional arguments:
  -h, --help     show this help message and exit
  -v, --verbose  enable debugging
  -l, --list     list known feeds or episodes if FEED is given
  -c, --curl     download instead of playing (experimental)
```

*A future version of "weo" will never enable you adding podcast-feeds without editing the JSON-formatted feeds-file. But you can fork this and make it happen.*


## License

No license.

