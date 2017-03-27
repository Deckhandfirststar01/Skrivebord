Functional Specifications for Private Search on Adblock Browser 2.0 (iOS)
=========================================================================

**Private Search is available for Adblock Browser™ 2.0 and higher on iOS** that allows users to search the mobile web without having their data collected, stored, tracked, or shared with third parties. The only data shared is the user's current location (and only if location detection has been enabled). This feature is enabled by default until the user selects a different Search Engine provider in the application Settings.

The purpose of this document is to fully explain how each and every feature of Private Search is intended to function from the user’s perspective. This document is NOT intended to describe any technical or visual requirements.

***

TABLE OF CONTENTS
-----------------

[**A: Web search results**](#a-web-search-results)

- [Web default view](#web-default-view)

- [First run view](#first-run-view)

[**B: Image search results**](#b-image-search-results)

- [Images default view](#images-default-view)

- [Size - options](#size---options)

- [Color - options](#color---options)

- [Number of results - options](#number-of-results---options)

[**C: Video search results**](#c-video-search-results)

- [Videos default view](#videos-default-view)

- [Duration - options](#duration---options)

- [Time - options](#time---options)

- [Quality - options](#quality---options)

[**D: Map search results**](#d-map-search-results)

[**E: References**](#e-references)

- [eyeo Hub Projects](#eyeo-hub-projects)

- [Contributors](#contributors)

***

A: WEB SEARCH RESULTS
---------------------

[Table of Contents](#table-of-contents)

### **Web default view**

![Web default view](/res/abb/abb-ios-private-search/A01-Web-default.png)

**OVERVIEW:** After entering a search term in the Adblock Browser Navigation bar, the user will be shown a list of Private Search results.

**A1:** The Navigation bar is hidden, and a Search bar with category buttons below are shown instead. In this example, the search term entered was "bicycles". Tapping the eyeglass icon on the right side of the Search bar will activate the field and launch the iOS system keyboard.

**A2:** The first category button is `WEB`, and is selected by default.

**A3:** Each search result is presented as an individual card. The first two cards in the list are paid search results and show the `<title of webpage>`, the exact `<URL>`, an `Ad label`, and a `<description>` of the webpage.

Tapping on a paid search result will reveal the Navigation bar, enter the destination URL in the address field, and load the corresponding page.

**A4:** Organic search results are shown below paid results, and at least the first organic result should always be partially visible above the application Tap bar. Each card shows the `<title of webpage>`, the exact `<URL>`, and a `<description>` of the webpage.

**A5:** Tapping the back arrow ("<") will return the user to the previous page they were viewing before entering a search term.

### **First run view**

![Firt run view](/res/abb/abb-ios-private-search/A02-First-run.png)

**A6:** When launching Private Search for the first time, the user will see a message card titled `Why use this search engine?` with a lock icon and text that says
> We'll never track, store, share, or sell your search data. We won't use your search queries for targeted advertising.

**A7:** Tapping the close button ("X") will remove the message and the search results below will slide up to fill the empty space. The message should never show again.

**A7:** Tapping the `DISMISS` button will remove the message and the search results below will slide up to fill the empty space. The message should never show again.

***

B: IMAGE SEARCH RESULTS
-----------------------

[Table of Contents](#table-of-contents)

### **Images default view**

![Images default view](/res/abb/abb-ios-private-search/B01-Images-default.png)

**B1:** Tapping the `IMAGES`category button shows only image search results.

**B2:** Related sorting options are displayed below the category selected.

**B3:** Thumbnail previews of image results are displayed in the content area. Tapping on a thumbnail will reveal the Navigation bar, enter the image URL in the address field, and load the full-sized image in a New Tab.

### **Size - options**

![Size options](/res/abb/abb-ios-private-search/B02-Images-size.png)

**B4:** Tapping `SIZE` displays a menu with more options. Tapping an option will update the search results show in the active category accordingly. Tapping the category button again, or anywhere outside of the menu area, will close the menu.

+ The first option is
> ALL SIZES

+ The second option is
> SMALL
>> _Smaller than **200px**_

+ The third option is
> MEDIUM
>>_Bigger than **600px**_

+ The last option is
> LARGE
>> _Bigger than **1200px**_

### **Color - options**

![Color options](/res/abb/abb-ios-private-search/B03-Images-color.png)

**B5:** Tapping `COLOR` displays a menu with more options. Tapping an option will update the search results show in the active category accordingly. Tapping the category button again, or anywhere outside of the menu area, will close the menu.

+ The first option is
> ALL COLOR

+ The second option is
> FULL COLOR

+ The third option is
> MONOCHROME

+ The fourth option is
> TRANSPARENT

+ The last option shows 6 colored squares, `<Red>`, `<Green>`, `<Blue>`, `<Pink>`, `<Yellow>`, and `<Purple>`. Tapping a square will show only images corresponding to the color selected.

### **Number of results - options**

![Number of results options](/res/abb/abb-ios-private-search/B04-Images-number-results.png)

**B6:** Tapping `NO. OF RESULTS` displays a menu with more options. Tapping an option will update the search results show in the active category accordingly. Tapping the category button again, or anywhere outside of the menu area, will close the menu.

+ The first option is
> ALL RESULTS

+ The second option is
> 25 RESULTS

+ The third option is
> 50 RESULTS

+ The last option is
> 100 RESULTS

***

C: VIDEO SEARCH RESULTS
-----------------------

[Table of Contents](#table-of-contents)

### **Videos default view**

![Videos default view](/res/abb/abb-ios-private-search/C01-Videos-default.png)

**C1:** Tapping the `VIDEOS`category button shows only video search results.

**C2:** Related sorting options are displayed below the category selected.

**C3:** Video search results are presented as cards. Each card displays the `<title of video>`, the `<source>` (e.g. YouTube), the `<time posted>` (e.g. - 3 years ago), and a preview image of the video which shows a `<play button>` and `<duration>` (e.g. 2:32).

Tapping on a card will reveal the Navigation bar, enter the video URL in the address field, and load the video webpage in a New Tab.

### **Duration - options**

![Duration options](/res/abb/abb-ios-private-search/C02-Videos-duration.png)

**C4:** Tapping `ANY DURATION` displays a menu with more options. Tapping an option will update the search results show in the active category accordingly. Tapping the category button again, or anywhere outside of the menu area, will close the menu.

+ The first option is
> ANY DURATION

+ The second option is
> SHORT
>> _0 to 4 minutes_

+ The third option is
> MEDIUM
>> _5 to 10 minutes_

+ The last option is
> LONG
>> _Longer than **10 minutes**_

###**Time - options**

![Time options](/res/abb/abb-ios-private-search/C03-Videos-time.png)

**C5:** The sort category name will change to the option selected accordingly. For video duration, the options are

+ `ANY DURATION`

+ `SHORT (0-4 MIN.)`

+ `MEDIUM (5-10 MIN.)`

+ `LONG (10+ MIN.)`

**C6:** Tapping `ANY TIME` displays a menu with more options. Tapping an option will update the search results show in the active category accordingly. Tapping the category button again, or anywhere outside of the menu area, will close the menu.

+ The first option is
> ANY TIME

+ The second option is
> PAST WEEK

+ The third option is
> PAST MONTH

+ The last option is
> PAST YEAR

The sort category name will change to the option selected accordingly.

###**Quality - options**

![Quality options](/res/abb/abb-ios-private-search/C04-Videos-quality.png)

**C7:** Press-and-swipe left to reveal hidden content when sort category names do not fit in the bar. 

**C8:** Tapping `QUALITY` displays a menu with more options. Tapping an option will update the search results show in the active category accordingly. Tapping the category button again, or anywhere outside of the menu area, will close the menu.

+ The first option is
> ANY QUALITY

+ The second option is
> LOW DEFINITION
>> _**360p** or less_

+ The third option is
> STANDARD DEFINITION
>> _**480p** or less_

+ The fourth option is
> HIGH DEFINITION
>> _**720p** or less_

+ The last option is
> FULL DEFINITION
>> _**1080p** or better_

The sort category name should reflect the option selected.

+ `ANY QUALITY`

+ `LOW DEF.`

+ `STANDARD DEF.`

+ `HIGH DEF.`

+ `FULL DEF.`

***

D: MAP SEARCH RESULTS
---------------------

[Table of Contents](#table-of-contents)

![Map Search Results](/res/abb/abb-ios-private-search/D01-Maps.png)

**D1:** Tapping the `MAPS` category button launches whichever map application the user has enabled by default. No actual results are show in Private Search. The user's search term and location (if known) are shared with map application.

**D2:** In this case, the user is being taken to Google Maps because that is the default map application enabled on their device.

***

E: REFERENCES
---------------------

[Table of Contents](#table-of-contents)

### **eyeo Hub Projects**

+ Product Request 153: [**New search results page**](http://hub.eyeo.com/issues/153)

+ **META** Product Request 151: [**New UI + Ghost Mode**](http://hub.eyeo.com/issues/151)

### **Contributors**

+ **Aaron Thornburgh**, Product Manager (owner of this document)

+ **Rotem Dar**, Business Developer

+ **Martin Velchevski**, Product Designer

***

_**Adblock Browser™** is a registered trademark of [eyeo GmbH](https://eyeo.com)._

