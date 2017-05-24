# The Adblock Plus notification system

Adblock Plus has a system for showing various types of notifications to users under certain conditions.

1. [What's missing from this document](#whats-missing-from-this-document)

2. [Notification updates](#notification-updates)

3. [Notification types](#notification-types)

4. [Closing and disabling notifications](#closing-and-disabling-notifications)

5. [When multiple notifications are supposed to be shown](#when-multiple-notifications-are-supposed-to-be-shown)

## What's missing from this document

The notification system is quite extensive, a few things are still missing from this document:

**Notification definition** - The format of the `notifications.json` file.

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

There are three different types of notification. They all contain translateable text and optionally links the user can visit. But they do differ when it comes to when and how they show up.

(Please note that the _question_ notification type is not specified here, because question notifications can currently not be defined via `notifications.json`, they are only used internally.)

### Information

#### When they show up

If the notification specifies _URL filters_, it does not show up before one of those filters matches. Otherwise, it shows up immediately after the notification update.

If the notification does not specify an _interval_, it shows up only once. Otherwise, it shows up each time it is triggered and the specified _interval_ has passed since the last time it was shown.

If the user has disabled information notifications, they never show up. See [closing and disabling notifications](#closing-and-disabling-notifications).

#### How they show up in Chrome

Information notifications trigger an animation in the icon:

![](/res/abp/notifications/information-icon.png)

And show up in the popup:

![](/res/abp/notifications/information-popup.png)

Both the icon animation and the notification in the popup stay in place until the user closes the notification, see [closing and disabling notifications](#closing-and-disabling-notifications).

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
