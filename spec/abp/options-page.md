# Options Page

Options page for the ABP Browser extension.

The options page is used to change various options of the ABP browser extension.

1. [Whitelist tab](#whitelist-tab)

## Whitelist tab

### Whitelist tab empty

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/whitelisted-websites.jpg' width='888px' />

<!-- TODO: make numbers in screenshot match numbered list below -->

1. [Whitelist tab headline](#whitelist-tab-headline)
1. [Whitelist tab description](#whitelist-tab-description)
1. [Add whitelisted domain textinput](#add-whitelisted-domain-textinput)
1. [Add whitelisted domain button](#add-whitelisted-domain-button)
1. [Add whitelisted domain error message](#add-whitelisted-domain-error-message)
1. [Empty Whitelist placeholder](#empty-whitelist-placeholder)

***TODO***: Number don't match.

#### Whitelist tab headline

Headline for the [Whitelist tab](#whitelist-tab) `Whitelisted websites`

#### Whitelist tab description

Description for the [Whitelist tab](#whitelist-tab).

```
You’ve turned off ad blocking on these websites. You will see ads on these websites. [Learn more](link to Help Centre article about whitelisting)
```

***TODO***: Add link to Help centre article

#### Add whitelisted domain textinput

Textinput to enter domains to be added to the whitelist.
 - Auto-focus when the [Whitelist tab](#whitelist-tab) is first loaded
 - Validate as you type

| Condition | Error message |
|-----------|---------------|
| Invalid hostname | `Not a valid hostname` |
| Duplicate hostname | `Website is already whitelisted` |


> Whats a valid hostname? <https://tools.ietf.org/html/rfc3986#section-3.2.2>

#### Add whitelisted domain button

Button to submit [Textinput A](#textinput-a).
 - Labelled `Add website`
 - Will only be active if [Add whitelisted domain textinput](#add-whitelisted-domain-textinput) is not empty and valid.

If clicked whitelist domain and show [Whitelisted domain added notification](#whitelisted-domain-added-notification).

> A whitelisted domain is an exception rule filter for a certain host.

#### Add whitelisted domain error message

Shows an error message if [Add whitelisted domain textinput](#add-whitelisted-domain-textinput) doesn't validate.

See [Add whitelisted domain textinput](#add-whitelisted-domain-textinput) for more details.

#### Empty Whitelist placeholder

Placeholder text shown as long as there are no whitelisted domains.

 - `You aren't whitelisting any websites yet.`
 - `Websites you trust and want to allow ads on will be shown here.`

### Whitelist tab populated

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/whitelisted-websites-populated.jpg' width='888px' />

1. [List of whitelisted domains](#add-whitelisted-domain-button)


#### List of whitelisted domains

The [List of whitelisted domains](#list-of-whitelisted-domains) displays all whitelisted domains. Show a [Remove whitelisted domain link](#remove-whitelisted-domain-link) for each domain.

<!-- This is to technical, find a better way to describe it -->
***Note***: *All whitelisted domains* does only refer to exception rules that match the following regexp and a member of the *SpecialSubscription* filter list:

```javascript
/^@@\|\|([^\/:]+)\^\$document$/
```

#### Remove whitelisted domain link

If clicked the corresponding whitelisted domain is removed.

*NOTE: recently added has been ommitted because we don't now the date of when a domain has been whitelisted so we could only show the domains that have been added since the option page has been opened and that doesn't make any sense?!*

### Whitelisted domain added notification

<!-- XXX: don't use html -->
<img src='/res/abp/options-page/whitelisted-websites-notification.png'
  width='888px' />

1. [Whitelisted domain added notification](#add-whitelisted-domain-button)

#### Whitelisted domain added notification

The notification should push down page from the top and disappear if the X is
clicked or automatically after 2 seconds.

`"{}" has been added as a whitelisted website`

***TODO***: Clarification needed
