# Open Social — User Review Results

Date: September 30, 2026. Session: approximately 22:06–22:52 CEST (Europe/Berlin).

**Outcome:** the available core social flows passed the checks performed. Two disposable accounts published short and long posts with and without images, exchanged replies and messages, established and removed friendship, and demonstrated the expected visibility of friends-only posts. One offline post was recovered through a single retry without an observed duplicate. This review remains incomplete for funded OSAT transactions, restoration into completely empty browser storage, and testing on a physical phone.

The [English feedback draft](FEEDBACK_FOR_REX.md) is ready for review.

## Environment and method

- Application: [opensocial.online](https://opensocial.online/).
- Environment displayed by the app: **Harbinger testnet**. No application release number was recorded.
- Computer: Mac mini M4, macOS 26.5 (25F71).
- Account A: Codex in-app browser, separate from the existing Chrome account.
- Account B: Chrome Incognito, Chrome 154.0.8037.58.
- Responsive checks: 390 × 844 CSS pixels. These are desktop browser viewport checks, not physical iOS/Android tests.
- Connection interruption: Chrome DevTools' **Offline** preset on B's test tab. Returned to **No throttling** after the test; DevTools closed. The computer's network settings were not changed.
- Method: live UI interaction, accessibility snapshots, screenshots, and observation from the second account. No code review or security audit was performed.
- Fixtures: fictional text, a 12-paragraph text of approximately 2.7 KB, accents and emoji, and a synthetic 480 × 320 checkerboard image with descriptive alt text.

The deployed interface differed from the linked testing guide. In this session, the app described free activity capacity and OSAT capacity as recovering over approximately **five days**, and reward votes as requiring paid capacity. The report follows the observed interface rather than treating older documentation as current behavior.

## Test accounts and published fixtures

| Account | Nickname | Address |
| --- | --- | --- |
| A | OSP Review A 20260930 | `1tktdidjqFzYKifsLQCoT3XTvdTtfPimG` |
| B | OSP Review B 20260930 | `1MzrBJT5sqxzK4iknqcxdbHnWS7fkxf16Y` |

Both accounts started with zero OSAT. Test content was labelled as a review and used fictional material. No messages were sent to real users. The existing Chrome user's account was used only for initial read-only observations.

| Fixture | Link |
| --- | --- |
| A short public post | [Post](https://opensocial.online/post/CMqvye20KgrOYO6aV6pK0SZA4M00upaXNXfO_f--jZM=) |
| B reply | [Reply](https://opensocial.online/post/RHHSOfabRHsMuiKx5MfHhEBbEw9ETqKD1aX-GyGaY_I=) |
| A long public post | [Post](https://opensocial.online/post/5sk2mSg3dYrZvxsw0xET37I0fq8IoZIyoVYvgVjkqfw=) |
| A short image post | [Post](https://opensocial.online/post/LNrmG3jhTcSkeKIGchfXNT71h9leYu_dpl_krISR6Qc=) |
| A long image post | [Post](https://opensocial.online/post/GhubJrC6OEow_sA7MSvLheOAfdOo_8kIKzSxQzvWKZI=) |
| A private post before friendship | [Post; account access required](https://opensocial.online/post/mXunSaiunWm7oGoTvmYwD9wHidg47wps6FRHEQek6J4=) |
| A public post at phone width | [Post](https://opensocial.online/post/HTvPQJx0MSFywM1gVHHExybo7r1Qn0DaWqMbQccbHuA=) |
| A reply at phone width | [Reply](https://opensocial.online/post/5PM08euxK265L5rgHguAoWnXTafzO2yw5mA-gIb2VFA=) |
| A private post after unfriending | [Post; account access required](https://opensocial.online/post/5GbWF2cSsavPRs_90C_TsTvDiO9wHSQU8BOfvEQ8YQw=) |
| B private post after unfriending | [Post; account access required](https://opensocial.online/post/zKq4Yt44va3hOAuvWb3Q18FGhdq-qzbMzlDByH3afZc=) |
| B offline/retry post | [Post](https://opensocial.online/post/_Qdbf_NpgjdAXWRGf1tTK6T_wRBZb3hLSZLEJBUGGtg=) |
| B post after identity import | [Post](https://opensocial.online/post/yTDrkG9S9AAOuSMJQJKr-t8o-cY9zt2NknWH5ftHkto=) |

The test content remains on testnet. No cleanup or permanent deletion was attempted.

## Results

“Pass” means the specific observed behavior matched the scenario. “Confusing” identifies a usability issue, not a failed transaction. “Pending” identifies an unexecuted test with its reason.

| ID | Scenario | Status | Observed result / evidence |
| --- | --- | --- | --- |
| U-01a | Create A and B; complete profiles | Pass | Both registered through the UI, saved nicknames and biographies, and subsequently published. [A profile](evidence/2026-09-30/06-account-a-profile.jpg). |
| U-01b | Find main features and regain access | Pass, limited | Navigation exposed feed, compose, profile, messages, settings, and tokens. Reload locked the account; the existing test passphrase unlocked it. B's saved identity remained available after closing and reopening its test window. Full browser quit/restart was not tested. |
| U-01c | Recovery explanation and backup | Pass / pending | Settings clearly warn that the identity file controls the account and excludes message history/keys. B's export was saved and its file existence verified privately. A's export showed “Saved”, but the automation did not obtain a verifiable file. The user completed B's identity-file import. The resulting unlocked account had the correct address, profile and readable private B1 post, and published a new test post that A could read. [Publication after import](evidence/2026-09-30/36-post-import-publication.png). Clean-profile/device restoration remains unverified because B's saved identity was still present before import. [Disclosure](evidence/2026-09-30/33-recovery-scope-disclosure.jpg). |
| U-02a | Short public text | Pass | B opened A's post. It remained available through a direct link and reload. |
| U-02b | Long public text | Pass | Twelve paragraphs, accents and emoji were displayed. The composer showed a byte budget (4067 bytes initially for text-only content); the test was comfortably below it. Maximum-size behavior was not tested. |
| U-02c | Short and long image posts | Pass | Both uploads published. The image rendered for A and B, including the long post's detail view. Initial “Loading photo…” states resolved. [Short image](evidence/2026-09-30/13-image-visible-to-b.png), [long image](evidence/2026-09-30/20-long-image-rendered-to-b.png). |
| U-02d | Image confirmation completeness | Confusing | The publish confirmation showed audience and text but no image preview, attachment count, or alt text. See UX-01 below. |
| U-03a | Reply and ordinary Like | Pass | B's reply appeared for A. B's Like remained selected with count 1 after reload/unlock. [Reply visible to A](evidence/2026-09-30/34-original-reply-visible-to-a.jpg), [Like](evidence/2026-09-30/09-reply-and-like.png). |
| U-03b | Upvote / downvote submission | Pending | Both controls opened a reward-vote dialog. It showed zero paid vote capacity and disabled confirmation. Neither direction was submitted. The downvote dialog was inspected, but its funded test on a different post remains pending. [Zero-capacity vote](evidence/2026-09-30/07-vote-zero-capacity.png). |
| U-03c | Remove or change reward vote | Unavailable | The interface described a vote as final and allowed one vote per account per public post. No editable reward-vote state was available to test. Ordinary Like is a separate feature. |
| U-03d | Cross-account delays | Pass, qualitative | Publication, images and message status moved through waiting states to visible results. Some profile counts and feeds updated later than the publishing state. Per-action latency was not measured systematically; there is no performance SLA conclusion. |
| U-04a | Find B; request and accept friendship | Pass | A requested friendship and B accepted. [Established friendship](evidence/2026-09-30/16-friendship-established.jpg). |
| U-04b | Private content before / after friendship | Pass | B could not read A's A0 post before friendship; after acceptance, B read the full earlier post. This matches the notice that new friends gain access to earlier private posts. [Before](evidence/2026-09-30/14-non-friend-cannot-read.png), [after](evidence/2026-09-30/17-private-after-friendship.png). |
| U-04c | Future private posts after unfriending, both directions | Pass | B removed A. A and B each published a new private post. Neither former friend could read the other's new text. B retained the earlier A0 content, as disclosed. [A→B blocked](evidence/2026-09-30/27-b-cannot-read-a-after-unfriend.png), [B→A blocked](evidence/2026-09-30/29-a-cannot-read-b-after-unfriend.jpg). This is a visibility check, not a cryptographic security certification. |
| U-05a | Enable messaging and handle connection setup | Pass | A's first message queued while B had not enabled messaging; the app explained the requirement. After B enabled messaging, A's queued message arrived without a manual resend. No separate accept-message screen was observed in this flow. |
| U-05b | Exchange messages and refresh history | Pass | A1 and B1 appeared in A's conversation, then remained after reload/unlock. A2 sent at phone width arrived in B's conversation. No duplicate was observed. [Delivery](evidence/2026-09-30/18-messages-delivered.jpg), [history](evidence/2026-09-30/19-message-history-after-refresh.ax.txt), [phone layout](evidence/2026-09-30/21-mobile-message.jpg). |
| U-05c | Close conversation | Pass | B closed it. The UI first showed “Closing · notifying peer”, then “Closed”. A subsequently also showed the conversation in the Closed view, with history and no message composer. [Peer closure](evidence/2026-09-30/30-peer-conversation-closed.jpg). Reopening and profile blocking were not tested. |
| U-06a | Balances, action capacity and limits | Pass / confusing | The Tokens page separates free actions, token capacity, ready-to-send OSAT, and recharging tokens. A had about 82 actions remaining near the end. The rules explain five-day recovery and separate Mana. The distinction between Like and paid reward votes requires additional explanation in the main social flow. [Rules](evidence/2026-09-30/15-token-rules-and-zero-balance.jpg). |
| U-06b | OSAT A→B and B→A transfers | Pending | Zero OSAT on both accounts. Entering B and amount 1 kept Send tokens disabled. No transfer was submitted, and receipt/balance changes are untested. [Transfer form](evidence/2026-09-30/31-zero-balance-transfer.jpg). |
| U-06c | Promotion cost / actual placement | Pass / pending | The dialog explained that 1 opportunity burns 1 fully charged OSAT permanently, gives a 1200-block window (about an hour), and does not guarantee views. Confirmation was disabled at zero balance. Actual burn and feed placement are untested. [Promotion](evidence/2026-09-30/23-promotion-zero-osat.jpg). |
| U-07a | Phone-width posting, reply and messaging | Pass, limited | A published a post and reply at 390 × 844, sent A2, and selected the synthetic image in the composer. Controls and text were usable. [Image picker](evidence/2026-09-30/25-mobile-image-picker.jpg), [persisted reply](evidence/2026-09-30/32-mobile-reply-persisted.jpg). Native touch, virtual keyboard, camera/photo-library behavior and a physical phone remain pending. |
| U-07b | Horizontal overflow | Pass | On the tested message layout, viewport width and document width were both 390 CSS pixels. An earlier public-profile viewport check also found no horizontal overflow. This does not cover every page or breakpoint. |
| U-07c | Direct link, reload, Back / Forward | Pass | A public post opened through its URL and survived reload. Browser Back / Forward navigated successfully in the initial public-post checks. Private links required unlock and then respected access rights. |
| U-07d | Offline publish and reconnect | Pass | B attempted one public post while Offline. The app showed an offline banner, kept it as “not sent”, and offered Try again / Edit saved post. After reconnecting, one retry published it. B's profile showed exactly one matching post; the same post appeared in A's view of B's profile. [Offline state](evidence/2026-09-30/26-offline-unsent-post.png), [single result](evidence/2026-09-30/28-offline-retry-single-post.png). One interruption/retry cycle was tested, not interruption after a transaction had already been broadcast. |

## Reproducible usability findings

### UX-01 — Publish confirmation omits image attachments

- **Impact:** minor to moderate; users cannot verify the full post in the final review step.
- **Steps:** create a Public post; add the synthetic photo and text; choose Review and publish.
- **Expected:** the final review includes the image or at least its attachment count and alt text, so the user can verify what will be permanently published.
- **Observed:** audience, publication notices and text appear; the attachment is visible only in the blurred composer behind the modal. Publication itself succeeds.
- **Frequency:** observed in the short-image confirmation; the long-image flow used the same text-focused confirmation. No claim of an image-upload failure.
- **Evidence:** [confirmation screenshot](evidence/2026-09-30/08-image-publish-confirmation.jpg).

### UX-02 — Private-post placeholder does not distinguish non-friends from pending key sharing

- **Impact:** makes the access requirement unclear.
- **Steps:** while unlocked as B, open A's private-post link before friendship; repeat with A's new private post after friendship removal.
- **Expected:** explain whether friendship is required or the reader is an eligible friend waiting for the author to finish sharing.
- **Observed:** both situations say the reader does not have the key “yet”, followed by an explanation about the author opening the app and automatic checking. The content remains correctly unreadable.
- **Frequency:** seen before friendship and after unfriending, including the reverse direction.
- **Evidence:** [before friendship](evidence/2026-09-30/14-non-friend-cannot-read.png), [after removal](evidence/2026-09-30/27-b-cannot-read-a-after-unfriend.png).

### UX-03 — The distinction between Like and reward voting is learned after opening another view

- **Impact:** a new user can expect an Upvote to behave like a free Like.
- **Steps:** create a zero-OSAT account, open another user's public post, select Upvote or Downvote, then inspect Tokens.
- **Observed:** Like works using activity capacity; reward-vote confirmation is disabled because paid capacity is zero. The dialog explains the reason, and Tokens explains the rules in detail. Main post controls do not convey this difference as clearly.
- **Suggestion:** put a short distinction, available paid capacity and the required cost beside the voting controls; give zero-balance testers a clear route to request an operator allocation. The disabled transfer form could also state why it is unavailable locally.
- **Evidence:** [vote dialog](evidence/2026-09-30/07-vote-zero-capacity.png), [Tokens](evidence/2026-09-30/15-token-rules-and-zero-balance.jpg).

No reproducible blocking functional failure was confirmed in the completed scenarios. These findings are usability observations. Waiting states that resolved are not labelled as failures.

## Remaining work

1. **Funded OSAT tests:** operator allocations for A and B are needed. Then cast an upvote and a downvote on different fictional posts, verify the displayed results after refresh, transfer a small amount in both directions, and promote one post. Reward settlement and multi-day recharge are also unverified.
2. **Clean-profile restoration:** the user completed the new local passphrase and identity-file import for B. The correct identity, private reading and a new publication visible to A were verified afterward. B's saved identity was present before import, so this does not establish recovery after complete loss of local browser storage. Repeat in a truly empty profile/device, including message-history behavior. [Imported profile and private reading](evidence/2026-09-30/35-imported-b-private-reading.png).
3. **A's export:** obtain and verify the actual identity file. The in-app export's “Saved” UI result alone was insufficient to verify a downloaded backup. This is an automation limitation, not a confirmed app defect.
4. **Physical phone:** repeat login, post, photo selection, reply and messaging on iOS/Android, including the virtual keyboard and touch controls.
5. **Optional coverage:** profile blocking, conversation reopening, multi-browser message-history linking, recovery contacts, maximum-size/invalid-media cases, and interruption after broadcast were not tested.

Recovery material is stored privately outside this workspace. It is excluded from reports and screenshots. Account A's in-app tab is retained for recovery follow-up. B's user-completed identity import was verified; its new local passphrase was entered by the user and is not recorded here. The original generated B passphrase must not be assumed valid after the user import. Temporary viewport overrides were reset.

## Evidence and source references

All session evidence is under [evidence/2026-09-30](evidence/2026-09-30/). Screenshots are observations at a point in time; accessibility snapshots may include transient loading states. The result rows explain which states subsequently resolved.

- [Executed plan](PLAN_REVIEW_USUARIO.md).
- [Rex's requested testing scope](https://t.me/c/4325237809/649).
- [Project testing guide](https://github.com/therexdev/Open-Social-Protocol/blob/HEAD/docs/v1-testing.md).
- [Feedback draft](FEEDBACK_FOR_REX.md).
