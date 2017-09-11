# The Adblock Plus notification system

Adblock Plus has a system for showing various types of notifications to users under certain conditions.

1. [What's missing from this document](#markdown-header-whats-missing-from-this-document)

1. [Notification updates](#markdown-header-notification-updates)

1. [Notification types](#markdown-header-notification-types)

1. [Closing and disabling notifications](#markdown-header-closing-and-disabling-notifications)

1. [When multiple notifications are supposed to be shown](#markdown-header-when-multiple-notifications-are-supposed-to-be-shown)

1. [Notification repository format](#markdown-header-notification-repository-format)

## What's missing from this document

The notification system is quite extensive, a few things are still missing from this document:

**Firefox behaviour** - The various notification types show up in slightly different ways in Firefox.

**Notification groups** - There is a mechanism for having notifications only appear for a random subset of the user base.

## Notification updates

ABP regularly checks the backend for notifications to show, which are defined in a file called `notification.json`. Since many notifications show up immediately after they have been downloaded, it is important to understand how this works.

### New users

For new users, notifications get downloaded one minute after the installation.

### Existing users

For existing users, notifications get downloaded roughly once per day, but it depends. The logic is as follows:

#### Update check frequency

One minute after starting ABP (e.g. the browser), and then every 60 minutes, ABP checks whether it needs to update notifications.

#### Update check logic

    if last update failed and was less than 24 hours ago then
      end check

    if last update was more than 48 hours ago then
	  update immediately, schedule next update in 24 hours
	  end check

    if last check was more than 24 hours ago then
	  delay the next update's scheduled time by the time that passed since the last check
	  end check

    if the scheduled time for the next update has passed then
	  update immediately, schedule next update in 24 hours
	  end check

## Notification types

There are four different types of notification. They all contain translatable text and optionally links the user can visit. But they do differ when it comes to when and how they show up.

(Please note that the _question_ notification type is not specified here, because question notifications can currently not be defined via `notifications.json`, they are only used internally.)

### Information

#### When they show up

If the notification specifies [URL filters](#markdown-header-urls), it does not show up before one of those filters matches. Otherwise, it shows up immediately after the notification update.

If the notification does not specify an _interval_, it shows up only once. Otherwise, it shows up each time it is triggered and the specified _interval_ has passed since the last time it was shown.

If the user has disabled information notifications, they never show up. See [closing and disabling notifications](#closing-and-disabling-notifications).

#### How they show up in Chrome

Information notifications trigger an animation in the icon:

![](/res/abp/notifications/information-icon.png)

And show up in the popup:

![](/res/abp/notifications/information-popup.png)

Both the icon animation and the notification in the popup stay in place until the user closes the notification, see [closing and disabling notifications](#closing-and-disabling-notifications).

### Normal

#### When they show up

The logic is the same as for information notifications.

#### How they show up in Chrome

Normal notifications show up in the popup:

![](/res/abp/notifications/normal-chrome-notification.png)

### Relentless

#### When they show up

The logic is the same as for information notifications, except that they cannot be disabled.

#### How they show up in Chrome

Relentless notifications do not change the icon or popup, but trigger a [Chrome notification](https://developer.chrome.com/apps/notifications):

![](/res/abp/notifications/relentless-chrome-notification.png)

### Critical

#### When they show up

The logic is the same as for relentless notifications, except that they show up every single time their condition is met (i.e. after each update check or whenever any of its _URL filters_ match), ignoring _interval_.

#### How they show up in Chrome

Like information notifications, critical notifications trigger an animation in the icon:

![](/res/abp/notifications/critical-icon.png)

And show up in the popup:

![](/res/abp/notifications/critical-popup.png)

Both the icon animation and the notification in the popup stay in place until the user closes the notification, see [closing and disabling notifications](#closing-and-disabling-notifications).

In addition to the popup, critical notifications show up as a [Chrome notification](https://developer.chrome.com/apps/notifications):

![](/res/abp/notifications/critical-chrome-notification.png)

## Closing and disabling notifications

### How it works in Chrome

**Notifications that show up in the popup** can be closed by clicking the _X_ icon, which presents two options: _Close this notification_ and _Stop showing notifications_:

![](/res/abp/notifications/popup-close.png)

_Close this notification_ will return the icon and popup to their original state.

_Stop showing notifications_ will do the same, but also disable this type of notification globally, i.e. the user will never see one of these unless they re-enable them again. This can be done in the _General_ tab on the options page by checking _Show useful notifications_ (this option only shows up if the user has disabled information notifications from the popup):

![](/res/abp/notifications/options.png)

Note, however, that not all [notification types](#notification-types) can be disabled.

**Notifications that show up as a Chrome notification** can be closed by clicking the _X_ icon, but there is no option for disabling them.

## When multiple notifications are supposed to be shown

ABP never shows the user more than one notification at a time. If multiple notifications are supposed to be shown, the notification with the highest _severity_ is shown first. If multiple notifications have the same _severity_, the first one listed in `notifications.json` is shown first.

Critical notifications have the highest severity, followed by relentless and information notifications.

After the first notification has been closed, the next notification will be shown the next time its condition is met (i.e. after the next update check or as soon as its _URL filters_ match). Note that critical notifications will show up each time their condition is met, and will therefore prevent all other notifications from being shown.


## Notification repository format

The notifications are stored in the [notification repository](https://hg.adblockplus.org/notifications/).

The notification repository format uses simple key value pairs. `Title` and `Message` are mandatory, the `severity` will default to *information* if omitted.


***NOTE***: The examples use javascript regular expressions do give an idea which values are valid, they don't necessarily define what is correct.

```javascript
/*
severity = normal

title.en-US = Test
message.en-US = Test
*/

severity = /^(information|normal|critical|relentless)$/
title./^[\w]{2}-[\w]{2}$/ = /^.+$/
message./^[\w]{2}-[\w]{2}$/ = /^.+$/
```
### Attributes

#### Severity

The severity (type) of the notification. Will default to *information* if omitted.

```javascript
// severity = Normal
severity = /^(information|normal|critical|relentless)$/
```

#### Title

The title of the notification. The title can be specified in multiple locales.
The default locale *en-US* is mandatory and must always be specified.

```javascript
// title.en-US = Title
title./^[\w]{2}-[\w]{2}$/ = /^.+$/
```

#### Message

The message of the notification. The message can be specified in multiple locales.
The default locale *en-US* is mandatory and must always be specified.

```javascript
// message.en-US = message
message./^[\w]{2}-[\w]{2}$/ = /^.+$/
```

#### Inactive

Don't show notification if inactive

```javascript
// inactive = yes
// inactive = no
inactive = /^(yes|no)$/
```

#### Variants

You can specify multiple variants and define the distribution across users
via the `sample` argument. The sample argument defines in percent (0.5 = 50%)
how many users will get this variant of the notification. If the percentages of
the variants don't add up (to 100%), the base notification will be distributed
in the remaining cases.


```javascript
/*
title.en-US = Base
message.en-US = Base

[0]
sample 0.25
title.en-US = Variant0
message.en-US = Variant0
[0]
sample 0.5
title.en-US = Variant1
message.en-US = Variant1
*/

title./^[\w]{2}-[\w]{2}$/ = /^.+$/
message./^[\w]{2}-[\w]{2}$/ = /^.+$/

[\d+]
sample = /^\d+(|\.|\.\d+)$/
title./^[\w]{2}-[\w]{2}$/ = /^.+$/
message./^[\w]{2}-[\w]{2}$/ = /^.+$/
```

#### Interval

Interval in milliseconds. Notification is shown every interval. Note regardless
of interval the notification will not be shown more often than
[update check frequency](#update-check-frequency).

#### Links

Space seperated list of [documentation links](/spec/adblockplus.org/documentation-link.md). For each entry there has to be a corresponding ```<a>``` tag in the message, the ```<a>``` tag will determine which part of the message will be linked (just like a normal ```<a>``` tag). If there are less ```<a>``` tags than links the superfluous links are ignored. If there are more ```<a>``` tags than links the superfluous ```<a>``` tags are ignored.

```javascript
/*
title.en-US = Title
message.en-US = Message with a <a>link</a>
links = chrome_support

title.en-US = Title
message.en-US = Message with a <a>link</a> and another <a>link2</a>
links = chrome_support knownIssuesChrome_filterstorage
*/
links = /([\w-_]+)+/
```

### Filters

It's possible to limit the users the notification will be shown to by using additional filters. A notification will show up if all filters are satisfied.

#### Target

A space seperated list of filters to only show notification to specific users.

Extension refers to the name and version of the browser extension (e.g. adblockplus).
Application refers to the name and version of the the browser (e.g. chrome).
Platform refers to the browser platform (e.g. chromium).
Locales show notifications based on the locale of the user
BlockedTotal shows notification based on the total number of ads blocked (*Prefs.blocked_total*).

```javascript
// target = extension=adblockplus extensionVersion=2.3.0.3702
// target = application=chrome applicationVersion<=1.5.0.964
target = /^(extension|application|platform)=\w+ \1Version(=|<=|=>)[\.\d]+$/
// target = locales=en-US
// target = locales=en-US,de-DE
target = /^locales=([\w]{2}-[\W]{2}[,]*)+$/
// blockedTotal=10
// blockedTotal>=10
// blockedTotal<=10
target = /^blockedTotal(=|<=|=>)\d+$/
// target = extension=adblockplus extensionVersion=2.3.0.3702 locales=en-US blockedTotal>=1000
```

If multiple targets are specified only one needs to be (fully) satisfied for the notification to show up.

```javascript
// target = (first AND second)
//                 OR
// target = (third AND forth)
target = application=chrome applicationVersion>=60.0
target = application=firefox applicationVersion>=55.0
```

#### Start

Don't show the notification before `start`.

```javascript
// start = '2017-07-24T12:00'
start = /^[\d]{4}-[\d]{2}-[\d]{2}T[\d]{2}:[\d]{2}$/;
```


#### End

Don't show the notification after `end`.

```javascript
// end = '2017-07-24T12:00'
end = /^[\d]{4}-[\d]{2}-[\d]{2}T[\d]{2}:[\d]{2}$/;
```
#### URLs

A space separated list of domains. The notification will only shown if the
users visits one of the specified domains.

```javascript
// urls = example.com
// urls = example.com foo.com bar.com
urls = /^[a-zA-Z0-9][a-zA-Z0-9-]{1,61}[a-zA-Z0-9](?:\.[a-zA-Z]{2,})+$/
```
