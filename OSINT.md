# OSINT Guide

There is no silver bullet when it comes to OSINT, some things will take time. Just work the problem, take the small wins and inch forward. And, of course, use these powers for good.

Additionally, be aware of operational security (OPSEC) - managing your online footprint (aka "attribution"). When conducting OSINT recon, you will leave a footprint behind. Be aware of this. Are the tools you're using tracking you/holding on to your data? If you obtained information privately, should you really blindly trust an unknown tool?

## Physical OSINT
Say you've been given an image and need to identify the location.

1. As a starting point, narrow the search area (e.g. to a country, state, city, etc.) - consider any context given.

    Too broad a search space can be paralysing, so narrow it down and have a crack  at _something_.
1. Identify points of interest
    * Distinct buildings
    * Foliage
    * Weather events
    * Architecture or style
    * Landscape
    * Potential references to locations, times, etc.
1. Gather info and search. Use tools to your advantage. Work the problem and narrow down possibilities. e.g.
    * Reverse image search
    * Look at maps and streetview to match area

---

## Digital OSINT
People are sloppy online. Whether that's leaking info on social media or committing a private key to a public repository. A combination of tools and Google-fu to help scour the web for you can help you quickly identify points of interest.

1. Scope the problem - what are you after?
2. Do some basic recon
    * Google-fu: filter sites, dates, etc.
    * Perform a domain lookup
    * Enumerate social media accounts
3. Follow up the interesting stuff
    * What can you do with the info you have? Does it unintentionally give away extra detail?
    * Look at archived versions of what you're after (perhaps a comment was deleted). Nothing really disappears from the internet


---

## Getting Stuck
This happens to everyone. Don't stress.

1. Take a break

    Disconnect from the problem so you can come back with fresh eyes. Don't try to solve it in the back of your head. _Disconnect_

1. Try the dumb stuff. It's often simpler than you think

    _"Surely not... No wa- oh, yep. That was it."_

1. Retry what you've already done

    Odds are that you were on the right track at some stage. Perhaps you just went a little wayward. Give it another go - use a different tool, modify your search query, change it up a little to see if it gets your further

1. Talk to someone

    Maybe you know someone with experience in a particular area. Use it. Or, oftentimes, you just need a rubber duck.

1. Fail fast

    Try something new for a little while - and before you get too attached to this new approach, is it worth pursuing?

---

## Tools
Tools are by no means the answer to absolutely everything, but they drastically speed up your process. Understand what it is doing on your behalf and don't be a script kiddie.

Below is a list of tools that are primarily free to use. Should this list fail you, [BlackArch](https://blackarch.org/social.html) has a great list of tools

### Physical
__Image Analysis__
* Reverse image searches
    * Google, Duckduckgo, bing, TinEye, Yandex, etc.
    * [Search By Image](https://chrome.google.com/webstore/detail/search-by-image/cnojnbdhbhnkbcieeekonklommdnndci) Chrome extension (includes Google, Bing, Yandex, etc.)
    * Add keywords to go with the search
    * Try cropping the image before searching, this may yield different results too.
* Google lens
* Exif tool, e.g. [Jeffrey's Image Metadata Viewer](http://exif.regex.info/exif.cgi)

__Maps__
* Apple, Google maps - Apple has some excellent 3D visualisations of major cities
* Google Earth - useful for annotating maps, saving sessions, examining flight paths, etc.
* Streetview and photospheres

__Wireless network mapping__
* [WiGLE.net](https://www.wigle.net/) - identify locations of SSIDs, MAC addresses, etc.

__People lookup__
* Social media
* Whitepages (Aus specific)
* Zoominfo.com + google-fu

__Weather events and historical data__  
You often just search until you find a site that suits your needs. Consider:
* Weather reports
* Bushfires


__Flights__  
Somehow this comes up more often than you'd think.  
_N.B. most sites only retain data for ~2 weeks_

* [Flightradar24](https://www.flightradar24.com/) (free-ish) - flight paths, historical data, etc.
* [WebTrak](https://www.airservicesaustralia.com/community/environment/aircraft-noise/webtrak/) (Aus only) - Used to track aircraft noise, but has decent historical data
* [Planemapper](https://www.planemapper.com/flights) and other various sites that containing info about plane regos, flight numbers, departure + arrival times, etc. With these sites, you often just search until you find one site that gives you the info you need.

### Digital
__Lookup tools__  
* [whois](https://who.is/)
* [viewdns.info](https://viewdns.info/)
* [emailrep.io](https://emailrep.io)

__Internet Archive__  
* [Wayback Machine](https://archive.org/web/)

__Social media enumeration__  
* [Whatsmyname](https://whatsmyname.app/), [Github](https://github.com/WebBreacher/WhatsMyName)
* Social-Analyzer, [Github](https://github.com/qeeqbox/social-analyzer)

__Google fu__
* Boolean searches `((a AND b) AND (c OR d)) NOT e`
  * Use `-e` to exclude results related to `e`
  * Use `+f` to include results related to `f`
* Advanced searching (Google dorking)
  * Ranges, e.g. `1..5`
  * Related `~term`
  * Filters:
    * `inurl:SECRET=`
    * `site:github.com`
    * `filetype:.pdf`
    * `intext:"resume"`
    * Date - `before:1989`, `after:1988-12-25`
  * Etc.
* Anonymous searching - use Google cache to avoid touching the website's server
  * `cache:<search>`
  * Copy the sites cache link: Kebab menu > "cached"
  * Paste URL and add `&strip=1` to view text-only version (so no images contact the server)

The interwebs are flooded with Google Fu cheatsheets.

__Paywall Bypass__
* [12ft.io](https://12ft.io)
* Browser dev tools


### Additional Resources
* [Tracelabs VM](https://www.tracelabs.org/initiatives/osint-vm) - a Kali box targeted towards OSINT. (The site also lists the tools included)
* [BlackArch Social Tools](https://blackarch.org/social.html) - list of tools
* https://coveryourtracks.eff.org - browser fingerprinting
* https://www.osintcombine.com/osint-bookmarks - list of useful bookmarks
* https://www.exploit-db.com/google-hacking-database
* https://www.bellingcat.com/
* https://inteltechniques.com/
* Chrome Extensions
  * [Web scraper](https://chrome.google.com/webstore/detail/scraper/mbigbapnjcgaffohmbkdlecaccepngjd)
  * [Screenshot tool](https://chrome.google.com/webstore/detail/gofullpage-full-page-scre/fdpohaocaechififmbbbbbknoalclacl)
  * [Search By Image](https://chrome.google.com/webstore/detail/search-by-image/cnojnbdhbhnkbcieeekonklommdnndci)
  * [Wayback Machine](https://chrome.google.com/webstore/detail/wayback-machine/fpnmgdkabkmnadcjpehmlllkndpkmiak)
