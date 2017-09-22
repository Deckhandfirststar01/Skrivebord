# ABP Firefox mobile: Options Page

Options page for the ABP Firefox mobile extension.

The options page is used to change various options of the ABP Firefox mobile extension.

### Index

1. [General requirements](#markdown-header-general-requirements)
1. [Firefox menu](#markdown-header-firefox-menu)
1. [Homescreen](#markdown-header-homescreen)
1. [Adding filter lists](#markdown-header-adding-filter-lists)
1. [Filter lists](#markdown-header-filter-lists)
1. [Assets](#markdown-header-assets)

### General requirements 
#### Bidirectionality
Any change of state will be immediately reflected in the options page regardless of where and how the change was made, so that the options page always reflects the current state of the extension.

- If a change to the state was made through other means e.g. auto update of filter list subscriptions, it will be reflected immediately in every instance of the options page.

The options page should also react to the following changes that may occur independently of the options page.

Affecting domain whitelist toggle:
- Filter got added
- Filter got removed

Affecting lists of filter lists and Acceptable Ads toggle:
- Filter list got added
- Filter list got disabled
- Filter list got enabled
- Filter list got removed
- Filter list title changed

### Style Guide
All UI patterns are defined in the [Options page Style Guide](/spec/abp/options-page-style-guide.md).

### Firefox menu
![](/res/abp/firefox-mobile-options-page/firefox_menu.jpg)

##### Overview 
Links to the Adblock Plus Options page.

Options page to open in a new tab

##### Link label
`Adblock Plus`

### Homescreen
![](/res/abp/firefox-mobile-options-page/firefox-mob-options-page.jpg)

#### Title 
`<h1>Adblock Plus settings<h1>`

#### Enabling/ Disabling Adblock Plus
Adblock Plus is enabled by default.

The toggle is "off" if current page is whitelisted and "on" otherwise.

Switching it to "off" will add a whitelist filter for the domain.

Switching it to "on" will
- remove all whitelist custom filters
- and disable all whitelist non-custom filters.

##### Toggle text
`Enable Adblock Plus on <website URL>`

#### Filter subscriptions
See [Filter subscriptions](#markdown-header-filter-subscriptions) for more details.

#### Enabling/ Disabling Acceptable Ads
Toggle to allow/ disallow Acceptable Ads

Opted-in by default.

Toggle subscribes/ unsubscribes the user from the Acceptable Ads filter list.

##### Toggle text
`Allow some nonintrusive advertising. [Learn more][1]`

[1]: Opens [Documentation link](/spec/abp/prefs.md#markdown-header-documentation-link): `%LINK%=acceptable_ads_criteria` in a new tab.

#### Filter subscriptions
![](/res/abp/firefox-mobile-options-page/firefox-mob-options-page.jpg)
![](/res/abp/firefox-mobile-options-page/firefox-mob-options-page-2-filter-lists.jpg)

##### Section title 
`Filter subscriptions`

##### Filter subscriptions list 
Lists all language filter subscriptions.

Display `Subscription title` in the list, as specified in the [Filter lists ](#markdown-header-filter-lists).

##### Bin icon 
Removes the filter list from the extension.

##### Button 
`+ ADD A FILTER LIST` button triggers the [Filter subscriptions layover](#markdown-header-filter-subscriptions-layover).

### Adding filter lists
Adding a filter list through an ABP auto-subscribe link from an external site will trigger the [Custom filter form](#markdown-header-custom-filter-form). 

The fields should auto-populate with the filter subscription title and URL link. 

#### Filter subscriptions layover
![](/res/abp/firefox-mobile-options-page/firefox-mob-options-page-filter-subscriptions.jpg)

##### Overview
List items are specified in [Filter lists](#markdown-header-filter-lists).

##### Behaviour
Scrollable area is fixed relative to the height of the screen size of the device. 

On larger screens, the modal dialog should extend in width to accommodate for the longest text length. And should extend vertically to the available space of the window.

Filter lists that have already been subscribed to will be greyed out and inactive.

Tapping anywhere outside of the modal dialog will close it.

##### Button
`+ ADD A CUSTOM FILTER LIST` button is fixed to the bottom of the layover. 

Selecting the button triggers the [Custom filter form](#markdown-header-custom-filter-form) in a modal window.

### Filter lists
Include only the language filter lists in the layover.

Refer to [Filter lists](/spec/abp/filter-lists.md) document for list of language filter lists to include.

#### Custom filter forms
![](/res/abp/firefox-mobile-options-page/firefox-mob-options-page-url-filter.jpg)
![](/res/abp/firefox-mobile-options-page/firefox-mob-options-page-url-filter-filled.jpg)

##### Title 
`Add a custom filter list`

##### Label text 1 
`Filter list name`

##### Label text 2 
`Filter list URL`

##### Behaviour 
- When a field is inactive or empty, the label text rests on the input area. 
- When a field is active or contains data, the label text floats above the input area.

##### Adding a filter list
`ADD FILTER LIST` subscribes to and enables the corresponding filter list, closes the form and adds the filter subscription to the bottom of the [Filter subscriptions ](#markdown-header-filter-subscriptions) list. 

##### Cancel
`CANCEL` button ignores all entries and closes the form. 

##### Behaviour
- On larger screens, the modal dialog should maintain its fixed height and extend to a maximum width of 25em.
- On smaller screens, the modal dialog should have a minimum width based on the width of the input fields (220px).  

See also [Filter subscriptions validation](#markdown-header-filter-subscriptions-validation)

#### Filter subscriptions validation

![](/res/abp/firefox-mobile-options-page/firefox-mob-options-page-url-validation.jpg)

When any text is added to the input field the error validation should dissappear.

| Error use case | Label | 
|-----------|---------------|
| No title entered | `Filter list title is required` |
| No URL entered | `A URL link is required` |

### Assets

| Name | Asset | 
|-----------|---------------|
| ABP_Logo_Outline.svg | ![](/res/abp/firefox-mobile-options-page/assets/ABP_Logo_Outline.svg) |
| checkmark.svg | ![](/res/abp/options-page/assets/checkmark.svg) |
| toggle-enabled.svg | ![](/res/abp/firefox-mobile-options-page/assets/toggle-enabled.svg) |
| toggle-disabled.svg | ![](/res/abp/firefox-mobile-options-page/assets/toggle-disabled.svg) |
| trash.svg | ![](/res/abp/options-page/assets/trash.svg) |





