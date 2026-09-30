# Open Social — Feedback Draft for Rex

Status: draft for review. Based on the [live user review](USER_REVIEW_RESULTS.md) on September 30, 2026.

Hey Rex — I ran a user-level review of opensocial.online on Harbinger with two disposable accounts, using macOS, Chrome and a separate in-app browser. I also checked a 390 × 844 phone-sized viewport. This was interface testing; it does not cover code, cryptographic security or the economic sustainability of the rewards model.

**What worked well**

- Both accounts registered and saved their profiles. Short and long posts, with and without an image, published and were visible to the other account. Replies and ordinary Likes worked, including persistence after refresh.
- Friendship and private-post visibility matched the notices: a non-friend could not read the test post; accepting friendship gave access to the earlier post; removing friendship prevented access to new private posts in both directions. Previously received content remained readable, as explained.
- Messaging handled the initial connection through a queue. A's first message arrived after B enabled messaging without manually resending it. Messages survived refresh/unlock. Closing the conversation eventually showed Closed on both accounts and preserved history. A simulated offline post was retained for retry, and reconnecting plus one retry produced one published post with no observed duplicate.

**Reproducible usability issues**

1. **The final image-post confirmation reviews text but not the attachment.** Add a photo, write text, and choose Review and publish: the modal shows audience and text but no photo preview, attachment count or alt text. The image does publish correctly. Including it would make the final review complete.
2. **The private-post access message is ambiguous for non-friends.** Before friendship, and again after unfriending, the placeholder says the reader does not have the key “yet” and talks about the author opening the app. It would help to distinguish “you need to be friends” from “you are a friend and key sharing is pending”. Access itself behaved correctly in our tests.

**My three priority UX suggestions**

1. Explain **Like versus reward Upvote/Downvote** directly beside the controls, with available paid capacity and the cost. A free Like works on a new account, while reward voting needs OSAT. The vote dialog explains this well once opened, but a newcomer only learns it after attempting a vote. A clear way for testers to request an allocation would help.
2. Include the photo/attachment details in the final publish confirmation.
3. Make private-post access messages state the reader's current eligibility and next step explicitly.

**Token experience**

The Tokens page separates free actions, paid capacity and charged versus recharging OSAT, and explains approximately five-day recovery and separate Mana. Promotion clearly describes a permanent OSAT burn, the 1200-block placement window, and the fact that views are not guaranteed. The zero-balance vote dialog also explains why confirmation is disabled.

Both new accounts had **zero OSAT**, so I could inspect these flows but could not validate funded voting, transfers, promotion placement, rewards settlement or recharge. Could you allocate test OSAT to these accounts for that follow-up?

- A: `1tktdidjqFzYKifsLQCoT3XTvdTtfPimG`
- B: `1MzrBJT5sqxzK4iknqcxdbHnWS7fkxf16Y`

**Limits of this review**

No blocking functional failure was confirmed in the completed flows. The phone check used a desktop viewport, so physical iOS/Android keyboard and photo-library behavior remain untested. B's identity-file export and user-completed import were verified, including the correct identity, private reading and a new publication visible from A, but restoration into completely empty browser storage is still pending; Settings clearly explains that the identity file excludes message history and messaging keys. I have not tested multi-browser message-history linking, recovery contacts or the long-term economics of the reward pool.

Screenshots, exact test-post links and reproduction steps are in the local results document. Recovery files and passphrases are excluded from the feedback.
