# Help Center

The Help Center goals are to: 
- Allow users to easily solve common questions/ problems for all eyeo products (Adblock Plus, Adblock Browser, Flatter Plus). 
- Provide relevant and easily consumable information to users.
- Be accessible for users of all technical skill levels and and thoroughly instruct from beginning to end.

**Note:** The first release of the Help Center will be focussed just on Adblock Plus help topics. 

1. [General navigation](#general-navigation)
1. [Product help home](#product-help-home)
1. [Article page](#article-page)
1. [Search bar](#search-bar)
1. [Search results page](#search-results-page)
1. [Imprint](#imprint)
1. [Articles table](#articles-table)
1. [Assets](#assets)

## General Requirements

### Style guide

All UI patterns are defined in the [Help Center Style Guide](/res/help-center/help-center-style-guide.pdf).

### WCAG
Should implement the following WCAG 2.0 Guidelines:
- 2.1 Keyboard Accessible

## General navigation

- To appear consistently across all pages.

### Help navigation

![](/res/help-center/abp-help-navigation.jpg)

1. [Logo](#logo)
1. [Site search bar](#site-search-bar)
1. [Product website link](#product-website-link)
1. [Language selector](#language-selector)
1. [Footer links](#foot-links)

#### Logo

- The eyeo help logo in the top left corner of the header, links back to the help center homepage (help.eyeo.com). 
- `eye/o help`
- Go to [Assets](#assets) for image assets.

#### Site search bar

- The site search bar will sit in the header of all pages. 
- Allows users to search help topics within that product area only (i.e. as a user in the Adblock Plus help area - www.help.eyeo.com/adblockplus, you can only search help topics related to Adblock Plus).
- The main homepage (www.help.eyeo.com) will be relesased once there is more than one product help center. The search bar on this page will allow the user to search help topics across all product help centers. 
- See [Search bar](#search-bar) for more details.
- Go to [Assets](#assets) for image assets.

#### Product website link

- [Adblock Plus](https://adblockplus.org) 

#### Language selection

- Language drop down menu that opens upwards.
- The Help Center will be available in 21 languages.
- Language to switch based on the browser locale setting.

| Language | Text in dropdown | 
|-----------|---------------|
| Czech | `noop:Čeština` |
| Spanish | `noop:Español` |
| French | `noop:Français` |
| German | `noop:Deutsch` |
| English | `noop:English` |
| Italian | `noop:Italiano` |
| Malay | `noop:Malayu` |
| Dutch | `noop:Nederlands` |
| Polish | `noop:Polski` |
| Portuguese | `noop:Português` |
| Russian | `noop:Русский` |
| Arabic | `العربيةnoop:` |
| Chinese (Simplified) | `noop:中文(简体)` |
| Chinese (Traditional) | `noop:中文(台灣)` |
| Greek | `noop:Ελληνικά` |
| Vietnamese | `noop:Tiếng Việt` |
| Turkish | `noop:Türkçe` |
| Thai | `noop:ภาษาไทย` |
| Japanese | `noop:日本語` |
| Korean | `noop:한국어` |

### Footer links

- `Legal` will open [Imprint](#imprint)
- `Privacy Policy` will open [Privacy Policy](https://adblockplus.org/privacy)
- `[Adblock Plus](https://adblockplus.org) is a registered trademark of [eyeo GmbH](https://eyeo.com)`
	
## Product Help Home 

- Product hub page for all articles related to Adblock Plus.
- Implement what is specified in the [General navigation](markdown-header-general-navigation).
- URL: www.help.eyeo.com/adblockplus
- Title: `Adblock Plus Help Center`
- Description: `Official Adblock Plus Help Center where you can find tips and tutorials on using Adblock Plus and other answers to frequently asked questions.`
- Go to [Assets](#assets) for image assets.

![](/res/help-center/abp-help-home.jpg)

1. [ABP help headline](#abp-help-headline)
1. [Popular topics](#popular-topics)
1. [Help categories](#help-categories)
1. [Contact section](#contact-section)

### ABP help headline

- `Adblock Plus Help Center`
- Go to [Assets](#assets) for assets.

### Popular topics

- Section headline `Popular topics`
- Float items across 2 columns. 
- Show up to 6 popular topics. The 6 popular topics will be fixed and defined by us. 
- Refer to [Articles Table](#articles-table) for article titles and text.

### Help categories

- Refer to  [Articles Table](#articles-table) for article titles and text.
- All Adblock Plus help center articles are grouped into the following categories:
	- `Customization & Settings`
	- `Troubleshooting & reporting`
	- `Installation`
	- `Adblock Plus for mobile`
- Go to [Assets](#assets) for image assets.

### Contact section

- Section header `Still looking for help?`
- Sub section 1
	- Title: `Get in touch`
	- Body: `Drop us a message on Twitter or Facebook and get your question answered ASAP.`
	- Opens in a new tab [Facebook](https://www.facebook.com/adblockplus)
	- Opens in a new tab [Twitter](https://twitter.com/AdblockPlus)
	- mailto:support@adblockplus.org
- Sub section 2
	- Title: `Looking for developers support?`
	- Body: `Find source code, release notes, advanced documentation and more.`
	- Opens in a new tab [Developer support](https://adblockplus.org/forum)
- Go to [Assets](#assets) for image assets.
	
## Article page 

- Implement what is specified in the [General navigation](markdown-header-general-navigation).
- URL: www.help.eyeo.com/adblockplus/ *article title*
- Title: *Article title*

![](/res/help-center/abp-help-article.jpg)

1. [Breadcrumb](#breadcrumb)
1. [Article title](#article-title)
1. [Browser detection](#browser-detection)
1. [Article](#article)
1. [Accordion menu](#accordion-menu)

### Breadcrumb

- `<PRODUCT> Help [1]` - `<Article title>`
- [1] [Product help home](#product-help-home)
	
### Article title

- Refer to  [Articles Table](#articles-table) for article titles and text.
- Go to [Assets](#assets) for image assets.

### Browser detection

- `Your browser:`
- Will detect the device’s browser and display the relevant browser specific article, where applicable.
- Drop down menu allows users to select articles that apply to other browser types.

### Article

- Refer to  [Articles Table](#articles-table) for article titles and text.
- Go to [Assets](#assets) for image assets.

### Accordion menu

- Refer to [W3 guidelines for Accordions keyboard](https://www.w3.org/TR/2016/WD-wai-aria-practices-1.1-20161214/#accordion).
- Accordion header: `<Category Title>` 
- Accordion panel: 
	- `List of articles`
	- Only display the first 2 lines of title if the article title is long.
- All product articles are listed in the accordion menu and grouped by categories replicating the groups on the homepage.
- The active category is expanded, and all other sections collapsed.
- Selecting to expand a different section, will automatically collapse other sections. 
- Go to [Assets](#assets) for image assets.

## Search bar

![](/res/help-center/abp-help-search-bar.jpg)

- Will use DuckDuckGo custom search. 
- Will perform a search across the specific area of the site the user is on - i.e. if on the Adblock Plus Help Center, it will only search for items within Adblock Plus Help.
- Results will be sorted by relevancy based on keywords and device platform.
- Search should be able to support spell checking and fuzzy searching. 
- Search results drop down
	-  Results to show in search results drop down when typing.
	- Limit the height of the search results drop down to 6 items.

## Search results page

![](/res/help-center/abp-help-search-results.jpg)

1. [Search results header](#search-results-header)
1. [Number of results](#number-of-results)
1. [Results](#results)

### Search results header

- `Search results for '<search term>'`

### Number of results

- `<Number of returned> Search results`

### Results

- Product icon
- `<Article title>`
- `<Article text>` - display only the first 2 line of texts. 

#### No returned results

![](/res/help-center/abp-help-search-no-results.jpg)

- `No results for '<search term>'`
- Display home page categroy items below.

## Imprint

![](/res/help-center/help-imprint.jpg)

- Title `Imprint`
- Description `eyeo GmbH is headquartered in Cologne, Germany. For support inquiries, message us at support@adblockplus.org`


`eyeo GmbH`

```
Lichtstraße 25
50825 Cologne
Germany
```
```
For additional support, go to:  [Adblock Plus Forum](https://adblockplus.org/forum/)
Email: support@adblockplus.org
Phone: +49 (0)221 7 65028 598
Fax: +49 (0)221 / 65028 599
Ust-IdNr: DE279292414
District Court: Köln HRB 73508
```
```
Managing Directors
Till Faida
Felix Dahlke
Steffen Kiedel
```

## Articles Table

| Article heading | Page name (URL) | Category | Popular topic? | Platform | Article text |
|---|---|---|---|---|---|
| `Block all ads` | block-all-ads | Customization & Settings | Yes | iOS | [blockads-adblockplusforios.md](/res/help-center/help-center-text/includes/blockads-adblockplusforios.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Chrome | [blockads-chrome.md](/res/help-center/help-center-text/includes/blockads-chrome.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Firefox | [blockads-firefox.md](/res/help-center/help-center-text/includes/blockads-firefox.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Internet Explorer | [blockads-internetexplorer.md](/res/help-center/help-center-text/includes/blockads-internetexplorer.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Maxthon | [blockads-maxthon.md](/res/help-center/help-center-text/includes/blockads-blockads-maxthon.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Opera | [blockads-opera.md](/res/help-center/help-center-text/includes/blockads-opera.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Safari | [blockads-safari.md](/res/help-center/help-center-text/includes/blockads-safari.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Samsung Internet | [blockads-samsung.md](/res/help-center/help-center-text/includes/blockads-samsung.md) |
| `Block all ads` | block-all-ads | Customization & Settings | Yes | Yandex | [blockads-yandexbrowser.md](/res/help-center/help-center-text/includes/blockads-yandexbrowser.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | iOS |  [removewhitelist-adblockplusforios.md](/res/help-center/help-center-text/includes/removewhitelist-adblockplusforios.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | Chrome |  [removewhitelist-chrome.md](/res/help-center/help-center-text/includes/removewhitelist-chrome.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | Firefox | [removewhitelist-firefox.md](/res/help-center/help-center-text/includes/removewhitelist-firefox.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | Internet Explorer | [removewhitelist-internetexplorer.md](/res/help-center/help-center-text/includes/removewhitelist-internetexplorer.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | Maxthon |  [removewhitelist-maxthon.md](/res/help-center/help-center-text/includes/removewhitelist-maxthon.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | Opera |  [removewhitelist-opera.md](/res/help-center/help-center-text/includes/removewhitelist-opera.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | Safari |  [removewhitelist-safari.md](/res/help-center/help-center-text/includes/removewhitelist-safari.md) |
| `Remove a website from the whitelist` | Remove-a-website-from-the-whitelist | Customization & Settings | No | Yandex Browser |  [removewhitelist-yandexbrowser.md](/res/help-center/help-center-text/includes/removewhitelist-yandexbrowser.md) |
| `Adblock Plus breaks the websites` I visit | broken-website | Troubleshooting & Reporting | Yes | Multiple | [adblock-plus-breaks-the-websites-i-visit.md](/res/help-center/help-center-text/pages/adblock-plus/adblock-plus-breaks-the-websites-i-visit.md) |
| `Add a website to the whitelist` | add-a-website-to-the-whitelist | Customization & Settings | No | Multiple | [add-awebsite-to-the-whitelist.md](/res/help-center/help-center-text/pages/adblock-plus/add-awebsite-to-the-whitelist.md) |
| `Add a filter list` | add-a-filter-list | Customization & Settings  | No | Multiple | [add-afilter-list.md](/res/help-center/help-center-text/pages/adblock-plus/add-afilter-list.md) |
| `Block malware sites` | block-malware-sites | Customization & Settings  | No | Multiple | [block-malware-sites.md](/res/help-center/help-center-text/pages/adblock-plus/block-malware-sites.md) |
| `Compatability issues` | compatibility-issues | Troubleshooting & Reporting  | No | Multiple | [compatibility-issues.md](/res/help-center/help-center-text/pages/adblock-plus/compatibility-issues.md) |
| `Configure automatic updates` | configure-automatic-updates | Customization & Settings  | No | Multiple | [configure-automatic-updates.md](/res/help-center/help-center-text/pages/adblock-plus/configure-automatic-updates.md) |
| `Disable social media buttons` | disable-social-media-buttons | Customization & Settings  | No | Multiple | [disable-social-media-buttons.md](/res/help-center/help-center-text/pages/adblock-plus/disable-social-media-buttons.md) |
| `Disable tracking` | disable-tracking | Customization & Settings  | Yes | Multiple | [disable-tracking.md](/res/help-center/help-center-text/pages/adblock-plus/disable-tracking.md) |
| `Download & install Adblock Plus` | download-and-install-adblock-plus | Installation  | No | Multiple | [download-and-install-adblock-plus.md](/res/help-center/help-center-text/pages/adblock-plus/download-and-install-adblock-plus.md) |
| `Hide the Adblock Plus icon` | hide-the-adblock-plus-icon | Customization & Settings  | No | Multiple | [hide-the-adblock-plus-icon.md](/res/help-center/help-center-text/pages/adblock-plus/hide-the-adblock-plus-icon.md) |
| `I still see ads` | i-still-see-ads | Troubleshooting & Reporting  | Yes | Multiple | [i-still-see-ads.md](/res/help-center/help-center-text/pages/adblock-plus/i-still-see-ads.md) |
| `Is Adblock Plus the same thing as Adblock?` | is-adblock-plus-the-same-thing-as-adblock | Popular Topics  | Yes | Multiple | [is-adblock-plus-the-same-thing-as-adblock.md](/res/help-center/help-center-text/pages/adblock-plus/is-adblock-plus-the-same-thing-as-adblock.md) |
| `Problems installing` | problems-installing | Installation  | No | Multiple | [problems-installing.md](/res/help-center/help-center-text/pages/adblock-plus/problems-installing.md) |
| `Remove a filter list` | remove-afilter-list | Customization & Settings  | No | Multiple | [remove-afilter-list.md](/res/help-center/help-center-text/pages/adblock-plus/remove-afilter-list.md) |
| `Remove a website from the whitelist` | remove-awebsite-from-the-whitelist | Customization & Settings  | No | Multiple | [remove-awebsite-from-the-whitelist.md](/res/help-center/help-center-text/pages/adblock-plus/remove-awebsite-from-the-whitelist.md) |
| `Unblock a blocked item` | unblock-ablocked-item | Troubleshooting & Reporting  | No | Multiple | [unblock-ablocked-item.md](/res/help-center/help-center-text/pages/adblock-plus/unblock-ablocked-item.md) |
| `Uninstall Adblock Plus` | uninstall-adblock-plus | Installation  | No | Multiple | [uninstall-adblock-plus.md](/res/help-center/help-center-text/pages/adblock-plus/uninstall-adblock-plus.md) |
| `What are Acceptable Ads?` | what-are-acceptable-ads | Popular topics  | Yes | Multiple | [what-are-acceptable-ads.md](/res/help-center/help-center-text/pages/adblock-plus/what-are-acceptable-ads.md) |

## Assets

| Asset name | Asset link | 
|-----------|---------------|
| [arro-icon-primary.svg](/res/help-center/assets/arro-icon-primary.svg) | ![](/res/help-center/assets/arro-icon-primary.svg) |
| [arrow-icon-secondary.svg](/res/help-center/assets/arrow-icon-secondary.svg) | ![](/res/help-center/assets/arrow-icon-secondary.svg) |
| [desktop-mobile.svg](/res/help-center/assets/desktop-mobile.svg) | ![](/res/help-center/assets/desktop-mobile.svg) |
| [email.svg](/res/help-center/assets/email.svg) | ![](/res/help-center/assets/email.svg) |
| [facebook.svg](/res/help-center/assets/facebook.svg) | ![](/res/help-center/assets/facebook.svg) |
| [installation.svg](/res/help-center/assets/installation.svg) | ![](/res/help-center/assets/installation.svg) |
| [logo-abb.svg](/res/help-center/assets/logo-abb.svg) | ![](/res/help-center/assets/logo-abb.svg) |
| [logo-abp.svg](/res/help-center/assets/logo-abp.svg) | ![](/res/help-center/assets/logo-abp.svg) |
| [mobile.svg](/res/help-center/assets/mobile.svg) | ![](/res/help-center/assets/mobile.svg) |
| [mobileIcon.svg](/res/help-center/assets/mobileIcon.svg) | ![](/res/help-center/assets/mobileIcon.svg) |
| [popular.svg](/res/help-center/assets/popular.svg) | ![](/res/help-center/assets/popular.svg) |
| [mobile.svreporting.svg](/res/help-center/assets/reporting.svg) | ![](/res/help-center/assets/reporting.svg) |
| [searchIcon.svg](/res/help-center/assets/searchIcon.svg) | ![](/res/help-center/assets/searchIcon.svg) |
| [settingsIcon.svg](/res/help-center/assets/settingsIcon.svg) | ![](/res/help-center/assets/settingsIcon.svg) |
| [twitter.svg](/res/help-center/assets/twitter.svg) | ![](/res/help-center/assets/twitter.svg) |
| [chrome](/res/help-center/assets/help-center-browser-icons/chrome.svg) | ![](/res/help-center/assets/help-center-browser-icons/chrome.svg) svg ![](/res/help-center/assets/help-center-browser-icons/chrome.png) png ![](/res/help-center/assets/help-center-browser-icons/chrome@2x.png) @2x.png  |
| [edge](/res/help-center/assets/help-center-browser-icons/edge.svg) | ![](/res/help-center/assets/help-center-browser-icons/edge.svg) svg ![](/res/help-center/assets/help-center-browser-icons/edge.png) png ![](/res/help-center/assets/help-center-browser-icons/edge@2x.png) @2x.png |
| [firefox](/res/help-center/assets/help-center-browser-icons/firefox.svg) | ![](/res/help-center/assets/help-center-browser-icons/firefox.svg) svg ![](/res/help-center/assets/help-center-browser-icons/firefox.png) png ![](/res/help-center/assets/help-center-browser-icons/firefox@2x.png) @2x.png |
| [internet-explorer](/res/help-center/assets/help-center-browser-icons/internet-explorer.svg) | ![](/res/help-center/assets/help-center-browser-icons/internet-explorer.svg) svg ![](/res/help-center/assets/help-center-browser-icons/internet-explorer.png) png ![](/res/help-center/assets/help-center-browser-icons/internet-explorer@2x.png) @2x.png |
| [ios](/res/help-center/assets/help-center-browser-icons/ios.svg) | ![](/res/help-center/assets/help-center-browser-icons/ios.svg) svg ![](/res/help-center/assets/help-center-browser-icons/ios.png) png ![](/res/help-center/assets/help-center-browser-icons/ios@2x.png) @2x.png |
| [maxthon](/res/help-center/assets/help-center-browser-icons/maxthon.svg) | ![](/res/help-center/assets/help-center-browser-icons/maxthon.svg) svg ![](/res/help-center/assets/help-center-browser-icons/maxthon.png) png ![](/res/help-center/assets/help-center-browser-icons/maxthon@2x.png) @2x.png |
| [opera](/res/help-center/assets/help-center-browser-icons/opera.svg) | ![](/res/help-center/assets/help-center-browser-icons/opera.svg) svg ![](/res/help-center/assets/help-center-browser-icons/opera.png) png ![](/res/help-center/assets/help-center-browser-icons/opera@2x.png) @2x.png |
| [safari](/res/help-center/assets/help-center-browser-icons/safari.svg) | ![](/res/help-center/assets/help-center-browser-icons/safari.svg) svg ![](/res/help-center/assets/help-center-browser-icons/safari.png) png ![](/res/help-center/assets/help-center-browser-icons/safari@2x.png) @2x.png |
| [samsung-internet](/res/help-center/assets/help-center-browser-icons/samsung-internet.svg) | ![](/res/help-center/assets/help-center-browser-icons/samsung-internet.svg) svg ![](/res/help-center/assets/help-center-browser-icons/samsung-internet.png) png ![](/res/help-center/assets/help-center-browser-icons/samsung-internet@2x.png) @2x.png |
| [yandex](/res/help-center/assets/help-center-browser-icons/yandex.svg) | ![](/res/help-center/assets/help-center-browser-icons/yandex.svg) svg ![](/res/help-center/assets/help-center-browser-icons/yandex.png) png ![](/res/help-center/assets/help-center-browser-icons/yandex@2x.png) @2x.png |












