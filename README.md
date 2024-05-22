# Remove AI Results from Google Search
Removes 'AI' Gemini generated content from the top of Google search results on Firefox as of May 22,2024. (Tested on desktop Firefox for Windows/macOS)
Instead now defaults searches to 'Web', which is what Google now names its traditional SEO search results links.

![google-search-filters](https://github.com/stevenya97/remove-ai-google/assets/10717304/1029d62c-79ee-42af-b1ad-6c98fb848835)

### Steps
With Firefox:
1. Do a regular Google search for a word.
2. Bookmark the search result page.
3. Go to the hamburger menu → Bookmarks → Manage Bookmarks.
5. (optional) Make a new folder for search and put the new bookmark in it. I use a 'Custom Search Shortcuts' folder
6. Edit the bookmark to include `udm=14` as a URL parameter, like this: `https://www.google.com/search?q=%s&udm=14`
7. Add a keyword(s) to trigger your custom search(I use `goog`).

![firefox steps example](https://github.com/stevenya97/remove-ai-google/assets/10717304/d7639b84-75d6-4867-83ff-0dbcf1117164)

To use, type in your keyword(s) into the search bar, add a space, and type your search query.

### Explanation

The URL `https://www.google.com/search?q=%s&udm=14` is used to insert your search query. `%s` is the typed query and `&udm=14` is appended to tell google to return a traditional `Web` search. The default `All` search can now include AI overviews and results. 'Web` includes just SEO links we all know and love.

![search-result](https://github.com/stevenya97/remove-ai-google/assets/10717304/cf7fce3b-e2ba-4389-8d28-a43482152a00)

### Misc.
In addition to these you will probably also want a couple of extensions/filters:
- [uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/)
    - Setup your [blocking mode](https://github.com/gorhill/uBlock/wiki/Blocking-mode)(optional, default lists are good enough for this)
    - Enable `AdGuard URL Tracking Protection`
    - Add `google.com##.GcKpu` to `My Filters`
    - Import [`Actually Legitimate URL Shortener Tool`](https://raw.githubusercontent.com/DandelionSprout/adfilt/master/LegitimateURLShortener.txt) - removes tracking elements from URLs
      - Check `Import` under `Filter Lists > Custom`
      - Paste in the linked URL above
      - Click `Apply Changes`
        
       ![image](https://github.com/stevenya97/remove-ai-google/assets/10717304/72c855c2-b553-4051-abb5-b09304fe111f)
- [uBlacklist](https://iorate.github.io/ublacklist/subscriptions#ai-generated-content) add filter lists that mass block known ai-domains and restores non-ai images to Google Images. [(github)](https://github.com/iorate/ublacklist)

### Removed
- ~~[Personal Blocklist (not by Google)](https://addons.mozilla.org/en-US/firefox/addon/personal-blocklist/) to remove over-SEOed sites that keep coming up on topics you search frequently~~ no longer maintained
- ~~[ClearURLs](https://addons.mozilla.org/en-US/firefox/addon/clearurls/) to remove tracking elements from URLs~~ redundant with uBlock Origin's `removeparam` and added lists.

Ideas and methods forked from [https://blog.zgp.org/custom-google-search/](https://blog.zgp.org/custom-google-search/) and [this r/Firefox post](https://www.reddit.com/r/firefox/comments/1cxmj14/remove_ai_from_google_search_on_firefox/)
