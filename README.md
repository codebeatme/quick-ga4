# Quick GA4
Quick GA4 (quick-ga4.js) is a free third-party lightweight minimized page script (JavaScript) for Google Analytics. It implements the main useful functions of the official GA4 script, including Page views, Scrolls, Outbound clicks, Site search, and File downloads in Enhanced measurement.

Here are the instructions for using Quick GA4，[GOOGLE ANALYTICS 第三方輕量最小化頁面腳本 QUICK GA4 使用說明](https://learnscript.net/zh-hant/google-analytics/toolkits/quick-ga4/)

# Using Quick GA4

```html
<script>
window['__GA4__'] = {
    // MEASUREMENT ID
    id: 'G-XXXXXXXXXX',
    // The url which the data is sent to, the default value is below, if you want, you can set up a proxy url
    url: 'https://www.google-analytics.com/g/collect',
    session: {
        // Session timeout, the default is 1800 seconds
        timeout: 1800,
        // Threshold for engagement time(A session will become an "engaged session"), the default is 10 seconds
        engagementMin: 10,
        // How engagement time is calculated, 'focus'(default) or 'visible'
        engagementType: 'focus'
    },
    event: {
        // The trigger condition of the event page_view, the default is '*'(page_view will always be triggered).
        pageView: '*',
        // An window event used to trigger the event user_engagement, the default is 'beforeunload'.
        userEngagement: 'beforeunload',
        // A CSS selector that points to a scrolled element which is used to determine whether the event scroll will be triggered, the default is 'body', set to null to disable the event scroll.
        scroll: 'body',
        // An Array of RegExp(or a string representing a regular expression) used to exclude domains, links containing these domains won't trigger the event outbound click, the default is [], set to null to disable the event outbound.
        outbound: [],
        // The search parameters that trigger the event view_search_results, the default is 'q,s,search,query,keyword', you can add additional search parameters by &(like 'q,s&name,age'), set to null to disable the event view_search_results.
        viewSearchResults: 'q,s,search,query,keyword',
        // An RegExp used to determine which elements on the page should be considered links to download archives, the default value is below, set to null to disable the event file_download.
        fileDownload: '(?<=\.)(pdf|xlsx?|docx?|txt|rtf|csv|exe|key|pp(s|t|tx)|7z|pkg|rar|gz|zip|avi|mov|mp4|mpe?g|wmv|midi?|mp3|wav|wma)$',
    },
    trigger: {
        // The page survival time needs to be greater than userEngagementMin(Seconds), otherwise, the event user_engagement will not be triggered.
        userEngagementMin: 1,
        // Threshold for scroll percentage, the default is 90, the event scroll will be triggered if the percentage is greater than or equal to scrollPercentMin.
        scrollPercentMin: 90
    },
    // This specifies whether to enable debugging mode
    debug: false
}
</script>
<script defer="true" src="<your path>/quick-ga4.js"></script>
```

# GitHub
https://github.com/codebeatme/quick-ga4
