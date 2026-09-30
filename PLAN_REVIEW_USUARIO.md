# Open Social User Testing Plan

Date: September 30, 2026.

Status: live user testing executed on September 30, 2026; funded OSAT actions, restoration into empty browser storage, and physical-phone coverage remain pending.

See [results and evidence](USER_REVIEW_RESULTS.md) and the [English feedback draft](FEEDBACK_FOR_REX.md). Checked items below record completed coverage; unchecked items explain the remaining scope.

## Objective and scope

Evaluate Open Social from a user's perspective: ease of getting started, reliability of everyday social tasks, and clarity of voting, promotion, and OSAT.

This first review consists of manual testing through the interface. It does not include code review, a security audit, exploit testing, or a comprehensive economic assessment of the tokenomics. Privacy checks will focus on what the test accounts can see; they do not certify the system's security.

## Context and sources

The group in the screenshot is **Project Phoenix (The Rebirth of Koinos)** on Telegram. Rex said his first priority is feedback on tokenomics and the role of tokens within the applications. For functional testing, he requested upvotes and downvotes, short and long posts with and without images, replies, messaging, promotion when OSAT is available, and sending/receiving OSAT.

- [Rex's specific request](https://t.me/c/4325237809/649).
- [Web application](https://opensocial.online/).
- [Project testing guide](https://github.com/therexdev/Open-Social-Protocol/blob/HEAD/docs/v1-testing.md).

The project identifies the environment as testnet. At the start, record the environment and version displayed by the application, if visible. Documented features may differ from those available in the deployed version.

## Preparation

- [x] Use two test accounts, A and B, in separate browser profiles or with two participants.
- [x] Record the date, device, operating system, browser, and browser version.
- [x] Prepare fictional text and test images without personal information.
- [ ] Keep recovery material for both accounts private, using the application's recovery options. **Partial: B's export is verified privately; A's export showed Saved but its downloaded file was not verified.**
- [x] Check whether OSAT is available. Do not assume it can be obtained through the interface.
- [x] Prepare a results log and screenshots without secrets or personal content.

There is no need to delete an existing account: separate profiles provide a clean starting state for testing. Do not include recovery files, keys, or passwords in the feedback.

## Proposed session: 90 minutes

The times are estimates. If a task blocks the rest of the session, record the issue and continue with independent tests that remain possible.

| Phase | Time | Tests | What to observe |
| --- | --- | --- | --- |
| Getting started | 15 min | Create an account, complete the profile, close the browser, and return. | Clear instructions, retained access, and ease of finding the main features. |
| Posts | 20 min | Publish short and long text, with and without an image; reply; upvote and downvote. | Successful publication, formatting, images, replies, and persistence after refreshing. |
| Relationships and messages | 20 min | Find the other account, request and accept friendship, post for friends, and chat. | Content visibility, requests, message delivery, and history after refreshing. |
| OSAT and promotion | 15 min | Check balances and limits; send and receive a small amount; promote a post if a balance is available. | Clear costs, confirmation of the outcome, resulting balances, and explanations of restrictions. |
| Everyday and mobile use | 20 min | Repeat the main tasks on mobile; navigate back, refresh, and test a connection interruption. | Usability, lost content, duplicates, waiting states, and uncertain outcomes. |

## Scenario checklist

### 1. Getting started

- [x] A and B create their accounts and complete their profiles.
- [x] It is clear whether the account is ready to post or another step is required.
- [x] The feed, post composer, profile, messages, and settings can be found without outside help.
- [x] Access can be regained after closing and reopening the browser. Checked reload/unlock and closing/reopening B's test window; full browser quit/restart not covered.
- [ ] The application explains how to retain or recover the account. Test restoration only with a test account and a private backup available. **Explanation and B export checked; B identity import and subsequent identity/private reading/new publication verified after user credential entry; restoration into completely empty browser storage remains pending.**

### 2. Posts, replies, and votes

- [x] A publishes a short text post without an image; B finds and opens it.
- [x] A publishes a long text post without an image; check formatting, readability, and stated limits.
- [x] Repeat the short and long posts with a test image.
- [x] B replies and A can see the reply.
- [ ] B upvotes and checks the result after refreshing. **Pending: zero OSAT / paid vote capacity; dialog inspected, confirmation disabled.**
- [ ] B downvotes a different fictional post and checks the result after refreshing. **Pending: zero OSAT / paid vote capacity; downvote dialog inspected, funded vote on a different post not submitted.**
- [ ] If the interface allows a vote to be removed or changed, check that the final state is consistent. **Unavailable: the observed reward-vote dialog says votes are final.**
- [x] Record how long each action takes to appear for the other account, without assuming an undocumented maximum delay. Waiting states and eventual cross-account visibility recorded qualitatively; systematic action timings were not collected.

### 3. Relationships, audience, and messages

- [x] A finds B and sends a friend request; B finds and accepts it.
- [x] A publishes a friends-only post and B can see it.
- [x] Before becoming friends, check that the other account cannot read a friends-only post, if the application allows one to be created.
- [x] If removing a friend is available, check what happens to new posts in both directions. Do not expect copies of earlier content to disappear.
- [x] A starts a conversation; check how message requests are explained and handled, if present.
- [x] A and B exchange messages and refresh to check the history.
- [x] If closing or blocking a conversation is available, check that its effect is clear and matches the interface's explanation. Closed on both accounts with retained history; reopening and profile blocking not covered.

### 4. OSAT, limits, and promotion

- [x] Identify the balance, available capacity, and restrictions shown by the application.
- [x] Record whether the purpose of OSAT and its relationship to available actions are understandable.
- [ ] If a balance is available, A sends a small amount to B; compare balances before and after, and check receipt. **Pending: both accounts have zero OSAT. A valid recipient and amount 1 kept Send tokens disabled.**
- [ ] If the interface permits it and a balance is available, B sends a small amount back to A. **Pending: zero OSAT; no funded transfer was submitted.**
- [ ] Promote a test post if OSAT and the feature are available. **Pending: feature available, but zero fully charged OSAT. Burn and placement were not executed.**
- [x] Check whether the cost and effect of promotion are explained before confirmation.
- [x] If balance or capacity is insufficient, record whether the message explains the reason and the next step.

There is no need to deliberately exhaust every limit. If a feature is missing or requires a balance we do not have, mark it as pending or unavailable rather than automatically classifying it as a failure.

### 5. Everyday and mobile use

- [x] Repeat posting, replying, and messaging on mobile. Executed at 390 × 844 CSS pixels on desktop; physical iOS/Android coverage remains pending.
- [ ] Check readability, keyboard behavior, image selection, and ease of using the buttons. **Partial: phone-width readability, controls and synthetic-file selection checked; physical-phone virtual keyboard and photo library untested.**
- [x] Open a direct link to a post and refresh it.
- [x] Navigate back and forward, and check that the interface remains understandable.
- [x] Briefly interrupt the connection during a test action and observe the outcome after reconnecting.
- [x] Before repeating an action with an uncertain outcome, check whether it has already appeared for the other account. Checked UI outcomes; only the explicitly failed offline post was retried, once. Final result showed one matching post.
- [x] Record ambiguous messages, lost drafts, or observed duplicates.

## Results log

Use these statuses: **pass**, **fail**, **confusing**, **pending**, and **unavailable**. Distinguish an observed failure from a suggested improvement.

| ID | Scenario | Account / device | Status | Observed result | Evidence |
| --- | --- | --- | --- | --- | --- |
| U-01 | Create an account and return | A / B, macOS | Pass / pending | Registration, return and B import verified; clean-profile restoration and A backup verification pending | [Results](USER_REVIEW_RESULTS.md) |
| U-02 | Short/long posts with/without an image | A / B | Pass / confusing | All four variants published; confirmation omits attachment preview | [Results](USER_REVIEW_RESULTS.md) |
| U-03 | Replies, upvotes, and downvotes | A / B | Pass / pending | Reply and Like passed; reward votes blocked by zero OSAT | [Results](USER_REVIEW_RESULTS.md) |
| U-04 | Friendship and friends-only posts | A / B | Pass | Before/after friendship and future visibility after removal checked in both directions | [Results](USER_REVIEW_RESULTS.md) |
| U-05 | Messages and history | A / B | Pass | Delivery, refresh history, and peer closure passed | [Results](USER_REVIEW_RESULTS.md) |
| U-06 | Sending/receiving OSAT and promotion | A / B | Pending | Zero OSAT; restrictions and promotion cost inspected, funded actions untested | [Results](USER_REVIEW_RESULTS.md) |
| U-07 | Mobile use, navigation, and reconnection | Desktop + 390 × 844 viewport | Pass / pending | Responsive tasks, links/navigation and offline retry passed; physical phone untested | [Results](USER_REVIEW_RESULTS.md) |

### Issue template

```text
ID and title:
Date and time:
Device, operating system, and browser:
Environment / visible version, if available:
Preconditions:
Steps to reproduce:
Expected result and reason:
Observed result:
Frequency: once / intermittent / always; number of attempts:
Impact: blocks a task / makes it difficult / minor detail:
Does it persist after refreshing?:
Screenshot or video without sensitive data:
Exact error message, if shown:
Operation identifier, if shown by the application:
Workaround that allowed testing to continue, if any:
```

## Feedback for Rex

Prepare an English summary with three parts:

1. **What works well:** concrete examples of completed tasks.
2. **Reproducible issues:** ordered by impact, with steps and evidence.
3. **Three priority improvements to the user experience:** especially clarity of account access, posting/messaging, and the role of OSAT, voting, and promotion.

Token feedback will focus on the user experience: what is understandable, what is confusing, whether the cost of each action is predictable, and what incentive the user perceives when using the application. Conclusions about the economic model require a separate review.

### Feedback draft structure

```text
We tested Open Social from a user perspective on [devices/browsers/date].

What worked well:
- [Observed examples]

Issues, ordered by impact:
- [Issue, reproduction steps, expected/actual result, evidence]

Our three main UX suggestions:
1. [Suggestion grounded in an observation]
2. [Suggestion grounded in an observation]
3. [Suggestion grounded in an observation]

Token experience:
- [What was clear or confusing about OSAT, votes, limits and promotion]

Not tested / blocked:
- [Unavailable features, missing balance or other limitations]
```

## Completion criteria for this review

- [x] Every scenario has a result or a specific reason why it remains pending.
- [x] Important issues have enough reproduction steps and evidence for Rex to investigate.
- [x] The summary distinguishes observations, suggestions, and untested features.
- [x] Three priority recommendations are grounded in observations.
- [x] The draft is ready for review before sending. This plan does not authorize sending it.

Completing this session establishes only the results of the manual tests performed on the recorded devices and under the recorded conditions.
