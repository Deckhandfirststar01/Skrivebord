# How to spec (a practical guide to functional specifications)

## Whats a spec (functional spec)?

Spec or specification in this document is always referring to a Functional Specification .

A functional specification describes all aspects of a product from a user's perspective.

All aspects really means all aspects: If there is a button in the ABP options page it belongs in the spec (obviously) but also if a resource is blocked by a filter it belongs in the spec (perhaps not so obvious).

## Why?

It helps to create better products:

Writing down the specifications forces you to actually design the Program.

Iterating over different designs in the specification is much faster than it is in actual code.

Words in a text file create less attachment than code written over several weeks and thus there is less reluctance to change it.

It saves time by reducing communication overhead:

Several people need to know how a program is supposed to work: QA to test it, Developers to implement it, Marketing to advertise it, Business to sell it and so forth. All this communication has to happen, if it happens ad hoc it’s not going to be very efficient.

The issues in our issue tracker (are supposed to) solve some of those issues but they have one big drawback: They only represent part of the program at a particular point in time. That means everybody (Product, QA, Developers, etc.) has to identify, read and build a mental model of all tickets that relate to a particular part of the Program each time they want to modify or very part of the Program. We cannot rely on everybody doing that and even if it would be very inefficient.

Without having a spec it’s impossible to have a schedule, if the Program hasn’t been designed there is no way of knowing how long will take.

A spec reduces day to day hold up by documenting (and forcing) design decisions. (What text should I use? What options should the dropdown offer? Etc…)

One author!
The spec has one author. He is responsible to figure out what the program is supposed to do and write the specifications.

Having only one author helps to ensure conceptual integrity. Individuals are less prone to escape responsibility while in a groups it’s hard to hold any one accountable.

A specification consists of many decisions (many of which are not important), an individual author can make decision more efficient and faster than a group of authors.

This doesn’t mean the author should not include other people in the analysis and design of the program, quite the contrary, team input is essential to ensure soundness and quality of the design, but the final specification should be written by one author and there should only be one person responsible for fixing the specification.

If it gets too much the specification can be broken up into several areas, each having its own author.

Individuals tend to perform better when there are multiple correct solutions.


## What?

The specification should contain every aspect of the program that is ascertainable by the user.

This includes the interface the user directly interacts with like buttons, dropdowns and windows but also things he not directly interacts with for example filter that hide elements in the webpage or that a filter list gets updated periodically. 

Detail, detail, detail. If you ask yourself the question whether or not you have described a filter detailed enough, the answer is probably no.

Human communication/language is very efficient in that it omits details that are known to all participants and can be deducted from the context of the communication. This is a problem when writing specifications because the context will change from when the specification is written to when it needs to be correctly interpreted. A programmer typically starts to implement a specification days after it has been written, the tests come weeks or month later and if you try to figure out how a particular feature behaves to asses if a certain behaviour is correct or not it might be years after original the author left the company.

It is therefore essential that the author forces himself to record every aspect of the program in unnatural detail.


### Examples:

#### Not enough detail:

Bad:

The user should be able to manage his filter list subscriptions.

Good:

List all filter list subscriptions below each other, newest first.

Show the name, a checkbox titled Enabled that is checked if the subscription is enabled, the last download date and an x icon for each subscription. Link the name to the url of the filter list. Remove the subscription if the user clicks on the x icon. En-/Disable the subscription if the user clicks on the checkbox.

Below the list of subscriptions show a button labeled Add filter subscription that opens the Add filter subscription dialog.

Not actionable, not enough detail:

Bad:

The button should update the subscriptions.

Good:

Upon clicking on the button labeled Update now the extension should try to download the current version for each enabled filter list subscription and update the last download date if the download was successful.


#### Not actionable:

Bad:

The Add filter subscription button should open the Add filter subscription dialog.

Good:

Clicking on the Add filter subscription button opens the Add filter subscription dialog.

#### Implementation details:

Bad:

Good:

## How (From Idea to specification)?:

New Feature or Not?

If the feature already exists in the product or exists in a similar form it should also be found in the specification in it’s current form.

It may be that the specification is younger than the product and the feature is not specified.

First question to answer is whether or not the idea already exists in the specification.

If it does it will not only not get designed twice but the person having the idea is saved the trouble to think through and formulate his idea so it can be communicated to his peers. 

If the specification contains a similar but not exactly the same feature the designed feature will still provide valuable insight for the new idea. The history of the feature even may reveal several different iterations of the feature which may directly match or provide even more insight if and how the idea might be valuable.

If the idea does not exist in the specification the person having the idea will at least be up to date on features relating his idea.

Second question should be if the feature already exists in the product?

If the specification is younger than the product it may be that this is an existing but unspecified feature.

If the idea already exists as a feature it needs to be specified but it doesn’t need to be designed, this has already happened in the product.

If the idea differs from the existing feature the new iteration needs to be designed and specified.

If the idea is doesn’t exist as a feature the idea needs to be designed and the result has to be specified.

Designing the Idea:

Designing an Idea means to build a mental model of an Idea that can then be evaluated through virtual exploration and experimentation.

This process is essential to figure out if an Idea is works and is worth pursuing further.

It’s a natural process of human thinking but doing it to the extent necessary for developing a Program (or any idea worth implementing for that matter) is quite unnatural. So if you are not actively pushing for it the design will probably not sophisticated enough.

Specifying the Design:

The written specification is the mental model brought to paper?

To write down the mental model as accurate as possible.

It’s again important to capture every detail of the mental model

Those two phases don’t strictly happen consecutively. In reality the author will go back and forth between those steps as he is refining the program and fleshing out the necessary details.


## VCS

At all times multiple versions of the specification need to be accessible, the version for the next release, the version for the current release or the version for the a past release. Additionally the history of the specification provides valuable insight (statistics, archeologie, etc).

Proposed specification changes are often times subject to discussions and undergo several feedback rounds before a final version is produced that can actually be implemented. 

A VCS with the ability to handle Pull/Merge Request is an ideal tool for both use cases, the specification should therefore reside in a VCS.

A common argument against a VCS, is that it is too complicated to use and too much effort to learn. If you think about it writing a specification for any worthwhile program is much more complicated than learning a VCS.

## Don’ts

Don’t describe the visuals of a program, long descriptions of visual aspects are tedious to read, a layout does a much better job of specifying how something should look like.

A lot if visual aspects are better defined in a styleguide (fonts, colors, defaults sizes, etc.). 

Don’t describe how something should be build, this is functional specification.


## FAQ:

### What if I want to add a new feature?

Specify the feature then create a ticket referencing the corresponding commit (or pull request) to the specification.

### What if i want to change an existing feature?

Change the existing specification and then create a ticket referencing the corresponding commit (or pull request) to the specification.

### What if the specification doesn’t match the implementation?

The specification has to be correct (spec == implementation) but it doesn’t necessarily has the last word in what correct is. Just like the source code that implements the Program, the specification is a complex document that can always contain errors. Regardless of who is correct and who is wrong it is a bug and has to be changed.

File a bug:

```
=== How to reproduce ===

1. TBA

=== Observed behavior ===
The spec doesn’t match implementation.

=== Expected behavior ===
The Spec should match the implementation.
```

### Found a bug?

Create a bug ticket as usual.
