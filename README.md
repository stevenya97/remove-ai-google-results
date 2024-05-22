# Remove AI Google
Removes 'AI' results from the top of Google search results on Firefox. (Tested on desktop Firefox for Windows/macOS)
Instead defaults searches to 'web', which is what Google now names its traditional links-based SEO search results.

# Steps
With Firefox:
1. Do a regular Google search for a word.
2. Bookmark the search result page.
3. Go to the hamburger menu → Bookmarks → Manage Bookmarks.
5. (optional) Make a new folder for search and put the new bookmark in it.
6. Edit the bookmark to include `udm=14` as a URL parameter, like this: `https://www.google.com/search?q=%s&udm=14`
7. Add a keyword or keywords to trigger your custom search(I use `goog`).


In addition to these you will probably also want a couple of extensions:

- ~~[Personal Blocklist (not by Google)](https://addons.mozilla.org/en-US/firefox/addon/personal-blocklist/) to remove over-SEOed sites that keep coming up on topics you search frequently~~ no longer maintained
- ~~[ClearURLs](https://addons.mozilla.org/en-US/firefox/addon/clearurls/) to remove tracking elements from URLs~~ redundant with uBlock Origin's `removeparam` and added lists.

- [uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/)
    - Setup blocking mode
    - Enable `AdGuard URL Tracking Protection`
    - Add `google.com##.GcKpu` to `My Filters`
    - Import [`Actually Legitimate URL Shortener Tool`](https://raw.githubusercontent.com/DandelionSprout/adfilt/master/LegitimateURLShortener.txt)
      - Check `Import` under `Filter Lists > Custom`
      - Paste in the linked URL above
      - Click `Apply Changes`
        
       ![image](https://github.com/stevenya97/remove-ai-google/assets/10717304/72c855c2-b553-4051-abb5-b09304fe111f)
- [uBlacklist](https://iorate.github.io/ublacklist/subscriptions#ai-generated-content) add filter lists that mass block known ai-domains and restores non-ai images to Google Images
