# Testing Websites/Pages

Testing web pages is more difficult than testing code as a rule, because it is hard to pin down what a web page should _do_. Specifications are often framed fairly vaguely, e.g. 'be easy to navigate', which leaves the test engineers with a problem: how do you know?

Traditionally a test-plan (at least for non user interface items) is framed something like this
Test ID | Do this | Expected Outcome | Actual Outcome
-------- | --------- | ---------------------- | -------------
079 | Press button A | 4p should appear in slot C | nothing happens

You are recommended to stick to this type of layout as far as possible.

The aims of a good test plan are that it should

- Test _all_ of the behaviour, ideally against the specification
- Be objective (it should not matter who is doing the testing _or what they already know_)
- Be repeatable, the results should be the same every time
  **Complete, objective, reproducible**
  Since web pages (as opposed to endpoints, APIs, etc) clearly involve idiosyncratic user actions and very often value judgements all of these aims are challenging to achieve.

_Ideally_ tests should also be _independent_, it should be possible to run any selection of tests in any order with the same results. Without this, the test suite itself may become 'fragile' (as new tests are added, older ones may stop working). Test independence can be hard to achieve fully, but where a test depends upon the system being in a particular state (maybe as a result of a previous test) this must (at least!) be carefully documented.

## What we should aim to test with web pages

### Test standards compliance

Do our HTML and CSS and JS pass code validation against the standards? We should also check legibility using online contrast checkers.

### Test consistency

Ideally the specification will state - and if not a view must be taken - of which browsers it is reasonable to support. These should be identified (down to version number) in the test plan and then all tests repeated with each browser. It is not normally reasonable to try to support _all_ browsers: IE6 anyone?
Use of colours and fonts and layout should be consistent.

### Test all interactive elements

Anything that responds in some way to user input should be tested. Things like buttons are fairly obvious, but do not overlook resizing the viewport, zooming, ...

### Test navigation

All hyperlinks and other navigation elements must be tested.

### Test Formatting

Everything should be sized correctly, nothing should overflow or 'blow out'. Graphics must be carefully checked for sizing, colour depth, etc. Check that everything behaves well at extreme sizes of the viewport.

### Test Content

Does everything load correctly?

Text **must** be proofread, **no** errors can be accepted on a public facing site. This should be done systematically, either content box by content box or against an asset list.

### Responsiveness\*

There should be targets for speed of loading. It can be hard (without specialist equipment) to make this really reproducible. Probably an average over several trials should be done. It can also be helpful (heading towards debugging and slightly away from testing) to look at web inspector to see where the loading time is being spent.

### Load testing\*

Commercial web sites should be tested under load with an expected number of users - this is virtually impossible to do without specialist equipment and must often be foregone on small sites.

---

(\*) These last two, and especially load testing, are server/network dependent also and we should keep our focus. Nevertheless unpleasant surprises should not happen.

## How to test

### Developer testing

Much of the above can and should be tested by the developers both during and after implementation. Ideally also by specialist QA engineers who are _not_ part of the development team.

Good change logs (records of all changes made, when , by whom, why) will help a lot too.

### User testing

There is no substitute for user testing. It does not matter if the navigation is working if none of the users can puzzle it out. It does not matter if colour and typography is consistent if all of the users hate it. Accessibility also needs attention and testing here.

### Automated testing

In the world of programming automated testing is highly favoured (the easier tests are to run, the more often they will be run and the more bugs will be caught early). It is objective, and lack of reproducibility will show up quickly. Also it is much cheaper. Automated testing is harder to do with web pages (traditional programming has the same problems with graphical UIs), but there are some good frameworks around to assist.

[Selenium](https://selenium.dev/) is one, very powerful, but complex to set up, [Cypress](https://www.cypress.io/) is a popular and easier to use alternative. Both are going to require some familiarity with programming. Either can be used to automatically test navigation, interaction ... almost anything except aesthetics and usability.

> (c) A P Oliver
> Written with [StackEdit](https://stackedit.io/).
