Functional Specifications for Adblock Browser 2.0 on iOS
========================================================

**Adblock Browser™ for iOS is a standalone application** that allows users to browse the mobile web without annoying, intrusive advertising. Adblock Browser 2.0 offers many new features that were previously unavailable in prior versions, such as a new private browsing feature called Ghost Mode, better management of bookmarked pages, and ungraded controls throughout.

The purpose of this document is to fully explain how each and every core feature of Adblock Browser 2.0 on iOS is intended to function from the user’s perspective. This document is NOT intended to describe any technical or visual requirements.

***

TABLE OF CONTENTS
-----------------

[**A: Basic User Interface**](#a-basic-user-interface)

- [Launching Adblock Browser](#launching-adblock-browser)

- [Primary User Interface](#primary-user-interface)

[**B: Dashboard**](#b-dashboard)

- [Dashboard default view](#dashboard-default-view)

- [Editing a Dashboard shortcut](#editing-a-dashboard-shortcut)

[**C: Navigation Bar**](#c-navigation-bar)

- [Entering search terms](#entering-search-terms)

- [Searching for text on page](#searching-for-text-on-page)

- [Entering a URL](#entering-a-url)

[**D: Control menu**](#d-control-menu)

- [Control menu default view](#control-menu-default-view)

- [Bookmarking pages](#bookmarking-pages)

- [Disabling ad blocking](#disabling-ad-blocking)

[**E: Recent History**](#e-recent-history)

- [Recent History default view](#recent-history-default-view)

- [Delete confirmation view](#delete-confirmation-view)

[**F: New Tabs**](#f-new-tabs)

- [New Tabs default view](#new-tabs-default-view)

- [Deleting a Tab](#deleting-a-tab)

[**G: Ghost Mode**](#g-ghost-mode)

- [Ghost Mode default view](#ghost-mode-default-view)

- [Managing New Tabs in Ghost Mode](#managing-new-tabs-in-ghost-mode)

- [Quitting Ghost Mode](#quitting-ghost-mode)

[**H: Bookmarked Pages**](#h-bookmarked-pages)

- [Bookmarked Pages default view](#bookmarked-pages-default-view)

- [Editing Bookmarked Pages](#editing-bookmarked-pages)

- [Deleting a Bookmarked Page](#deleting-a-bookmarked-page)

[**I: Settings**](#i-settings)

- [Settings default view](#settings-default-view)

- [Ad blocking options](#ad-blocking-options)

- [Clear Data options](#clear-data-options)

- [Clear Data confirmation message](#clear-data-confirmation-message)

- [Language options](#language-options)

- [Search Engine options](#search-engine-options)

[**J: Conditional States**](#j-conditional-states)

- [First run - Dashboard](#first-run---dashboard)

- [First run - Navigation bar](#first-run---navigation-bar)

- [Critical error](#critical-error)

[**K: References**](#k-references)

- [eyeo Hub Projects](#eyeo-hub-projects)

- [Contributors](#contributors)

***

A: BASIC USER INTERFACE
-----------------------

[Table of Contents](#table-of-contents)

### **Launching Adblock Browser**

![Splash Screen](/res/abb/abb-ios/01A-Splash-screen.png)

**OVERVIEW:** When launching Adblock Browser 2.0, the user should always see a start up screen while the application loads. The purpose of this screen is to inform or remind them that they are using _this_ application, and not some other ad blocking browser.

**A1 - Splash screen:** After tapping the application icon on their Apple device, the user will see one of two splash screens while Adblock Browser loads in the background. In this case, everything is loading properly and the user sees a prominent logo with the message, 
> from the makers of **Adblock Plus**

To see what happens when things go wrong, [click here](#critical-error).

### **Primary User Interface**

![Basic Elements](/res/abb/abb-ios/01B-Basic-elements.png)

**OVERVIEW:** Once loaded, Adblock Browser 2.0 was specifically designed to offer users one-tap access to all the primary features through a single User Interface. Any secondary features are confined to temporary states. This way users can focus on the content (not the browser), stay on task, and avoid confusion. The interactions and visual presentation of elements are also intended to be simple, intuitive, and easy to understand. As a result, users should always feel completely in control of their browsing experience.

**A2 - Navigation bar:** When a user launches the app, the first thing they probably want to do is enter either a web address or search term. To facilitate these primary actions, a large search field is displayed above the content area. When viewing a webpage the user will see the primary domain (e.g. adblockplus.org), a star icon on the left (Bookmark Page/Remove Bookmark), and a Refresh Page icon on the right.

**A3 - Control menu:** After navigating to a Web page, a user then may want to access page-level functions, such as bookmarking or sharing content. These controls are available by tapping the Control icon in the Navigation bar.

**A4 - Content area:** This is where all content will be displayed, whether it is a webpage or a Settings menu.

**A5 - Tap bar:** From here, the user can view the next or previous page (if applicable), create and manage New Tabs, switch between browsing modes, or access their bookmarks with a single tap.

***

B: DASHBOARD
------------

[Table of Contents](#table-of-contents)

### **Dashboard default view**

![Dashboard view](/res/abb/abb-ios/02A-Dashboard-view.png)

**OVERVIEW:** Whenever a user opens a New Tab, or launches the Adblock Browser for the first time, they will see shortcuts to their most popular destinations on the web until a URL or search term has been entered in the Navigation bar. At first they will only see shortcuts to [adblockplus.com](https://adblockplus.org/) and [acceptableads.com](https://acceptableads.com/) until there are sites from their actual browsing history to show.

A blank Navigation bar should always display prompt text that says,
> Search or enter address…

**B1:** Each shortcut is represented by a capital letter in a square with a label beneath. Icons should reflect the first letter of the base URL (e.g. “A” for **A**cceptableads.com) and, if known, the primary brand color. Otherwise, a color will be assigned randomly. The label should be the actual title of the website (e.g. “Acceptable Ads”). Tapping an icon will take a user directly to the destination URL homepage.

**B2:** A “TIP” icon and message should appear below the icons, stating 
> Tap and hold any icon to edit or remove.

### **Editing a Dashboard shortcut**

![Dashboard edit](/res/abb/abb-ios/02B-Dashboard-edit.png)

**B3:** Tap and holding an icon will display tooltip controls above it. Tapping `Edit` will load the actual URL in the Navigation bar and launch a standard iOS keyboard, allowing the user to edit the website or webpage entered. Tapping `Remove` will delete the shortcut from the user’s Dashboard, and all other icons that were to the right, and/or below, should slide into their new positions accordingly.

***

C: NAVIGATION BAR
-----------------

[Table of Contents](#table-of-contents)

### **Entering search terms**

![URL bar search](/res/abb/abb-ios/03A-URL-bar-search.png)

**OVERVIEW:** Tapping the Navigation bar activates the field and launches the iOS system keyboard. The star icon (Bookmark Page) disappears and the Refresh Page icon is replaced with an Delete (“X”) icon. As the user types into the field, search term or URL suggestions will appear in a list below. Tapping the X icon clears the Navigation bar field.

**C1:** The user should always have full editing capabilities for text, including the ability to select segments of a term or URL.

**C2:** Tapping the `Cancel` button disregards the text entered, hides the keyboard, and restores the previous view.

**C3:** If applicable, the very first option in the list below will be to search for text on a page the user is currently viewing, and should be labeled as `Find <term> on page`, with `<term>` being the exact text entered in the Navigation bar.

**C4:** All other suggested search terms will depend on the Search Engine the user has enabled.

**C5:** The keyboard should always be the iOS default, and is not a custom Adblock Browser feature.

### **Searching for text on page**

![Page search](/res/abb/abb-ios/03B-Page-search.png)

**C6:** If the user choose to search for text on a content page, then the search term entered will appear in the Navigation bar.

**C7:** All instances of the term on the page in view will highlighted in yellow.

**C8:** Tapping the Done button restores the previous Navigation bar and Tap bar states.

**C9:** The Tap bar will be replaced with text indicating the current and total number of matches, Back (“<“) and Next (“>”) icons, and a Done button.

### **Entering a URL**

![Swipe to previous page](/res/abb/abb-ios/03C-Swipe-to-previous-page.png)

**C10:** Tapping an gray star icon in the Navigation bar will bookmark the current page in view. Tapping a blue star icon will remove the bookmark from the page.

**C11:** Tapping the Refresh Page icon will reload and the contents recache the page in view.

**C12:** If applicable, a user may swipe left or right at any time to view the next or previous page. The corresponding domain URL should appear in the Navigation bar above.

**C13:** Alternatively, the user may also tap the Previous Page (“<“) or Next Page (“>”) buttons in the Tap bar.  The corresponding domain URL should appear in the Navigation bar above.

***

D: CONTROL MENU
---------------

[Table of Contents](#table-of-contents)

### **Control menu default view**

![Control menu default](/res/abb/abb-ios/04A-Control-menu-default.png)

**OVERVIEW:** The user can access the Control menu from the primary User Interface at any time. From this menu, a user may disable ad blocking on the current domain, open a New Tab, Bookmark pages, Share a webpage, view their Recent History, or vgo to the application Settings.

**D1:** Tapping the Control menu icon will show a list of options below. Tapping the icon again will close the menu.

**D2:** The first menu item is `Block Ads on this Site` and displays a toggle. By default, the toggle is green to indicate that ad blocking is enabled. Tapping the toggle (or list item row) will disable ad blocking on the website in view and add the domain to the user’s Whitelisted Websites.

**D3:** The second menu item is `Open New Tab`. Tapping this option closes the Control menu and shows a default Navigation bar and Dashboard view in a New Tab.

**D4:** The third menu item is `Add Bookmark`. By default, the icon appears in a gray outline. Tapping this option bookmarks the page in view.

**D5:** The fourth menu item is `Share`. Tapping this option closes the Control menu and displays a standard iOS dialogue menu allowing the user to share the page in view to social media, or email the destination URL.

**D6:** The fifth menu item is `History`. Tapping this option closes the Control menu and displays a list of the user’s Recent History.

**D7:** The last menu item is `Settings`. Tapping this options closes the Control menu and displays the Settings view.

**D8:** Tapping anywhere in the content area below the last list item will close the Control menu.

### **Bookmarking pages**

![Bookmark this page](/res/abb/abb-ios/04B-Bookmark-this-page.png)

**D9:** If the page in view has been bookmarked, the star icon in the Navigation bar will appear solid blue. Tapping this icon will remove this bookmark from the page.

**D10:** When viewing the Control menu for a Bookmarked Page, the list option will say `Remove Bookmark` and the icon will appear in solid gray. Tapping the icon or list row will remove the bookmark from the page in view, revert to the default list row state, and change the star icon in the Navigation bar to a gray outline.

### **Disabling ad blocking**

![Disable ad blocking](/res/abb/abb-ios/04C-Disable-ad-blocking.png)

**D11:** The toggle is gray whenever ad blocking has been disabled. Tapping the toggle will enable ad blocking on the website in view and remove the domain from the user’s Whitelisted Websites.

***

E: RECENT HISTORY
-----------------

[Table of Contents](#table-of-contents)

### **Recent History default view**

![History](/res/abb/abb-ios/05A-History.png)

**OVERVIEW:** After tapping `History` from the Control Menu, the user is taken to a dedicated list view of their `Recent History`. This list should be shown in reverse-chronological order, with the the most recent webpage visited at the top of the list.

**E1:** Tapping the `Done` button returns the user to the previous page they were using before accessing the Control menu.

**E2:** Tapping the `Delete` button displays a message asking the user to confirm the action.

**E3:** Each item displayed in the Recent History list shows an icon (first letter of the domain in a square), the webpage title, and full URL.

**E4:** List items are groups by day, are are indicated by a list section header (e.g. MONDAY, JAN 1, 2018)

### **Delete confirmation view**

![Delete History](/res/abb/abb-ios/05B-Delete-History.png)

**E5:** After tapping the Delete button, a message window and dark layover appear over the Recent History list. The message title is `Delete Recent History?`, and the text is 
> This action cannot be undone. Are you sure you want to continue?

**E6:** Tapping the `Cancel` button dismisses the message and restores the Recent History list view.

**E7:** Tapping `Continue` button dismisses the message and deletes all of the user’s Recent History, producing an empty list view.

***

F: NEW TABS
-----------

[Table of Contents](#table-of-contents)

### **New Tabs default view**

![New Tabs default](/res/abb/abb-ios/06A-New-Tabs-default.png)

**OVERVIEW:** Tapping the New Tab icon in the Tap bar takes the user to a dedicated page which allows them to add or delete individual Tabs.

**F1:** Tapping the `Add New Tab` button generates an empty Tab that appears directly beneath (but above the most recently created or viewed New Tab).

**F2:** An empty New Tab will show a blank thumbnail image and the label `New Tab (X)`, with `(X)` representing the corresponding Tab number. Tapping an empty New Tab will launch the Dashboard view and default Navigation bar.

**F3:** If previously a New Tab has been launched and a destination URL has been entered, a Tab will subsequently display a thumbnail of the last page the user had viewed, along with the webpage title, favicon, and domain address. Tapping a loaded Tab should launch the webpage last viewed on that domain.

**F4:** A `TIP` icon and message should appear below the icons, stating
> Swipe tabs left to close them.

**F5:** Tapping the center New Tab icon will always return a user to the New Tabs view, regardless of what they where viewing previously. The number of open Tabs should always display in the center, even if that number is 0 or 99 (maximum).

### **Deleting a Tab**

![Delete New Tab](/res/abb/abb-ios/06B-Delete.png)

**F6:** Swipe left to delete a Tab. As the user swipes, white text that says `Close` appears on a red background. If the user does not swipe completely to the left edge of the screen, the Tab will slide back into its original position on release.

![Undo delete](/res/abb/abb-ios/06C-Undo-delete.png)

**F7:** The `TIP` message should disappear once the user has successfully deleted a Tab for the first time.

**F8:** After successfully deleting a Tab, a message and button appear at the bottom of the New Tab page. Text appears on the left,
> You closed a tab.

On the right, an `UNDO` button appears. Tapping this button immediately restores the previously deleted Tab in its original position.

***

G: GHOST MODE
-------------

[Table of Contents](#table-of-contents)

### **Ghost Mode default view**

![Ghost Mode default](/res/abb/abb-ios/07A-Ghost-Mode-default.png)

**OVERVIEW:** A user can browse the mobile web privately at any time by tapping the ghost icon in the Tap bar to activate Ghost Mode. To visually distinguish this feature from normal browsing mode, the primary User Interface for Ghost Mode is black with white, purple, or gray text.

**G1:** By default, a user will see an empty Navigation bar and a message (instead of the Dashboard).

**G2:** Displayed beneath a prominent ghost icon, the message title is `Ghost Mode`, and the text is
> While in Ghost Mode, all browser history, search history, web forms, cookies, and temporary internet files will not be stored on your device.
This message appears until the user has entered a search term or URL in the Navigation bar above.

**G3:** A `TIP` icon and message should appear below the icons, stating
> Tap the icon to deactivate Ghost Mode when you are finished with the session.

**G4:** Tapping the ghost icon anytime while in normal browsing mode will switch to this view in Ghost Mode. From here, a user can either enter a search term in the Navigation bar above, or tap the center icon in the Tap bar below to open a New Tab in Ghost Mode.

### **Managing New Tabs in Ghost Mode**

![Ghost Mode New Tabs](/res/abb/abb-ios/07B-Ghost-Mode-New-Tabs.png)

**G5:** When in New Tabs view for Ghost Mode, a `TIP` icon and message should appear below any open Tabs, stating 
> Tabs are not stored in your history and will be closed when you quit Ghost Mode. 
This message appears until the user has entered a search term or URL in the Navigation bar above.

**G6:** Tapping the center New Tab icon anytime while browsing privately will return a user to the New Tabs view for Ghost Mode. The number of open Tabs should always display in the center, even if that number is 0 or 99 (maximum).

**G7:** Tapping the ghost icon anytime while in Ghost Mode will show a message window asking the user whether or not they would like to end their current private browsing session.

### **Quitting Ghost Mode**

![Quit Ghost Mode](/res/abb/abb-ios/07C-Quit-Ghost-Mode.png)

**G8:** The message title is `Quit Ghost Mode?`, and the text is 
> Your history will not be stored and all active tabs will be closed.
The Navigation bar and Control menu are not accessible in this view.

**G9:** Tapping the `OK` button dismisses the message, exits Ghost Mode, deletes all open tabs and recent browsing history, and returns the user to the page they viewed most recently in normal browsing mode (white User Interface).

**G10:** Tapping the `Cancel` button dismisses the message and restores the current view.

***

H: BOOKMARKED PAGES
-------------------

[Table of Contents](#table-of-contents)

### **Bookmarked Pages default view**

![Bookmarked Pages default](/res/abb/abb-ios/08A-Bookmarked-Pages.png)

**OVERVIEW:** The user can quickly view a list of their `Bookmarked Pages` by tapping the right-most icon in the Tap bar. Any pages bookmarked by tapping the star icon, either in the Navigation bar or from the Control menu, will show in this list.

**H1:** Tapping the `Edit` button shows the user new controls allowing them to delete and reorder their Bookmarked Pages.

**H1:** Each list item displays a thumbnail of the last page the user had viewed, along with the webpage title, favicon, and domain address. Tapping a loaded Tab will launch the corresponding webpage.

**H3:** Tapping the Bookmarked Pages icon anytime while in normal mode will take the user to this view.

### **Editing Bookmarked Pages**

![Edit Bookmarks](/res/abb/abb-ios/08B-Edit-Bookmarks.png)

**H4:** Tapping the `Done` button restores the default state of the Bookmarked Pages list.

**H5:** Tapping the Delete icon (red circle with white horizontal line) will launch another view with more options.

**H6:** The user can press-and-drag any list item into a new position.

### **Deleting a Bookmarked Page**

![Delete Bookmark](/res/abb/abb-ios/08C-Delete-Bookmark.png)

**H7:** Tapping the `Cancel` button returns the user to the list of their Bookmarked Pages.

**H8:** A Bookmarked Page may display on the user’s Dashboard (depending on the recency and frequency of page views) by default. This is indicated by a green toggle. Tapping the toggle will disable this feature and remove the shortcut from the Dashboard (if show), and prevent it from displaying in the future (until the user taps the toggle again to enable).

**H9:** Tapping the `Delete Bookmark` button returns the user to the list of their Bookmarked Pages and remove the list item.

***

I: SETTINGS
-----------

[Table of Contents](#table-of-contents)

### **Settings default view**

![Settings default](/res/abb/abb-ios/09A-Settings.png)

**OVERVIEW:** Tapping the Settings icon or list row from the Control menu will launch the `Settings` view. Any further controls not shown on this page are always just 1-2 taps away. All options are grouped by category.

+ The first category is `ADBLOCK BROWSER`.

+ The second category is `SEARCH`.

+ The last category is `VERSION`.

**I1:** Tapping the `Done` button returns the user to the previous content page they were viewing.

**I2:** The first option is `Ad blocking` and is turned `On` by default. Tapping the row will switch the toggle to `Off` and disable this feature globally in the application. Tapping the “>” arrow displays more Ad blocking options.

**I3:** The second option is `Clear Data`. Tapping the “>” arrow displays further options.

**I4:** The third option is `Languages`. Tapping the “>” arrow displays a list of languages in which ad blocking is supported.

**I5:** The fourth option is `Search Engine`. Gray text displays the current Search Engine in use. Tapping the “>” arrow displays more options.

**I6:** The fifth option is `URL Search Suggestions`. Unless this feature was previously disabled during first run of the application, suggestions are enabled by default. This is indicated by a green toggle. Tapping the toggle will disable this feature.

**I7:** The final list item is text only, and displays the application version number (e.g. “v2.0.0).

### **Ad blocking options**

![Settings ad blocking](/res/abb/abb-ios/09B-Ad-blocking.png)

After tapping the option `Ad blocking`, a user will see more options. All options are grouped by category.

+ The first category is `ACCEPTABLE ADS`. The text reads:
> Choose whether to include nonintrusive, non-animated ads that adhere to strict criteria. [Learn more](https://acceptableads.com/en/about/criteria).

+ The second category is `WHITELISTED WEBSITES`. The text reads:
> You have turned off ad blocking on these websites and will see ads on them.

**I8:** Tapping the `Settings` button returns the user to the previous default Settings view.

**I9:** The user may choose one of three ad blocking options.

+ The first option, `Show nonintrusive ads`, is selected by default, and the user will see Acceptable Ads when browsing websites that have not been whitelisted. 

+ Tapping the second option, `Show nonintrusive, privacy friendly ads`, will show only Privacy Friendly Acceptable Ads. 

+ Tapping the last option, `Hide all ads`, will block any ads on any website.

**I10:** Any website the user has disabled ad blocking on from the Control menu will appear in this list with a green toggle. Tapping a toggle will remove the corresponding domain from the list and enable ad blocking on that website.

### **Clear Data options**

![Clear Data](/res/abb/abb-ios/09C-Clear-Data.png)

After tapping the option `Clear Data`, a user will see more options.

+ `Clear History`

+ `Clear Cache`

+ `Clear Cookies and Site Data`

+ `Clear Everything`

**I11:** Tapping any of the options will show a message window asking the user to confirm the action.

### **Clear data confirmation message**

![Clear Data confirmation message](/res/abb/abb-ios/09D-Clear-Data-confirm.png)

**I12:** The message title should correspond to the option selected, such as

+ `Clear History?`

+ `Clear Cache?`

+ `Clear Cookies and Site Data?`

+ `Clear Everything?`

and the text for each is
> This action cannot be undone. Are you sure you want to continue?`

**I13:** Tapping the `Cancel` button dismisses the message and restores the previous view.

**I14:** Tapping the `Continue` button dismisses the message, deletes all data related to the option selected, and restores the previous view.

### **Language options**

![Settings Languages](/res/abb/abb-ios/09E-Languages.png)

After tapping the option `Languages`, a user will see more options. All options are grouped by category.

+ The first category is `BLOCK ADS FOR WEBSITES IN`

+ The second category is `OTHER LANGUAGES`

**I15:** The language enabled by default is determined by the user's location, and is indicated by a green toggle. Tapping the toggle will disable ad blocking in that language.

**I16:** All other languages supported are turned off by default, and are indicated by gray toggles. Tapping a toggle will enable ad blocking for the corresponding language.

### **Search Engine options**

![Settings Search Engine](/res/abb/abb-ios/09F-Search-Engine.png)

After tapping the option `Search Engine`, a user will see a list of options.

**I17:** The first option, `Private search` `*`, is selected by default. Tapping another list item `**` will change the default Search Engine used by the application to the corresponding provider.

`*` _Although customized for Adblock Browser users, Private search is developed and maintained by a separate company. [Click here](http://hub.eyeo.com/issues/153) for more information._

`**` _Actual secondary Search Engine providers will be provided separately, and should be approved by an eyeo Legal Representative before final implimention._

***

J: CONDITIONAL STATES
---------------------

[Table of Contents](#table-of-contents)

### **First run - Dashboard**

![Dashboard first run 1](/res/abb/abb-ios/10A-Dashboard-first-run-1.png)

**OVERVIEW:** After launching the application for the very first time, a user will see a series of messages before they can start browsing the web. These message will inform them about important options available to them at all times.

**J1:** The title of the first message is `Allow “Adblock Browser” to access your location while using the app?`, and the text is:
> We only give websites (e.g. Google Maps) access to your location if you give permission. Adblock Browser does not use your location for any other purposes.

**J2:** Tapping the `Don’t allow` button dismisses the message and shows the Dashboard view, but location detection will be disabled when searching the web.

**J3:** Tapping the `Allow` button dismisses the message, shows the Dashboard view, and enables location detection when searching the web.

![Dashboard first run 2](/res/abb/abb-ios/10B-Dashboard-first-run-2.png)

**J4:** The second message title is `You’re always in control!`, and the text is:
> Annoying ads are always blocked, while nonintrusive ads are allowed by default. To change this setting anytime, go to: 

>**Control menu > Settings > Ad blocking**

**J5:** Tapping the `Got it` button dismisses the message and shows the Dashboard view.

### **First run - Navigation bar**

![Search first run](/res/abb/abb-ios/10C-Search-first-run.png)

**J6:** After tapping the Navigation bar for the very first time, the user will see a message and two buttons. The message title is `URL Search Suggestions?`, and the text is:
> Tap Yes if you want to see web search results. To change this setting at anytime, go to: 

> **Control menu > Settings > Search Suggestions**

**J7:** Tapping the `No` button dismisses the message. No search suggestions will show when the users types a term or URL into the Navigation bar.

**J8:** Tapping the `Yes` button dismisses the message. Search Suggestions will show once the user begins typing a term or URL, and is generated by the Search Engine provider currently enabled.

### **Critical error**

![Splash Error](/res/abb/abb-ios/10D-Splash-Error-screen.png)

Occasionally something will go wrong and the application either crashes or closes improperly. Whenever this happens, the user will see a special slash screen the next time they launch Adblock Browser.

**J9:** When launching the application after a critical error, a generic message displays beneath an icon:

+ H1: `Uh-oh!`

+ H2: `Something went wrong.`

+ Text:
> A critical error prevented Adblock Browser from starting. Follow the steps below to quit the app and try again.

+ Step 1:
> Double-tap the Home button.

+ Step 2:
> Swipe up on Adblock Browser to quit the app.

+ Step 3:
> Restart Adblock Browser.

***

K: REFERENCES
---------------------

[Table of Contents](#table-of-contents)

### **eyeo Hub Projects**

+ **META** Product Request 151: [**New UI + Ghost Mode**](http://hub.eyeo.com/issues/151)

+ Related Product Request 153: [**New search results page**](http://hub.eyeo.com/issues/153)

### **Contributors**

+ **Felix Dahlke**, Chief Technology Officer

+ **Aaron Thornburgh**, Product Manager (owner of this document)

+ **Mario König**, Technical Project Manager

+ **Martin Velchevski**, Product Designer

+ **Lisa Bielik**, Content Manager

+ **Tamara Blasco**, Translations Manager

+ **Julian Doucette**, Prototype Developer

+ **Philip Hill**, Quality Assurance Manager

***

_**Adblock Browser™**, **Adblock Plus™**, and **Acceptable Ads™** are registered trademarks of [eyeo GmbH](https://eyeo.com)._
