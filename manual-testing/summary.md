# Team Summary

> Draft in progress. Sections marked _To be added_ will be completed once each member's work is merged into `main`.

## Guided Testing Coverage

### Login Testing

Required coverage:
- Valid credentials.
- Incorrect password.
- Missing password.
- Missing username.
- Recovery after an invalid attempt.

Results:
- Valid credentials (LOGIN-P01, member-a): Pass — [View record](results/member-a.md#login-tests)
- Incorrect password (LOGIN-N01, member-b): _To be added_
- Missing password (LOGIN-N02, member-c): Pass — [View record](results/member-c.md#test-id-login-n02)
- Missing username (LOGIN-N03, member-d): Pass — [View record](results/member-d.md#test-id-login-n03)
- Recovery after an invalid attempt (LOGIN-R01, member-a): _To be added_

### Equivalence Partitioning

Required coverage:
- Age below the accepted range.
- Age within the accepted range.
- Age above the accepted range.

Results:
- Age 10 (AGE-EP-10-B, member-b): _To be added_
- Age 30 (AGE-EP-30-A, member-a): Pass — [View record](results/member-a.md#equivalence-partitioning)
- Age 90 (AGE-EP-90-C, member-c): Pass — rejected by the browser before submission ("Value must be less than or equal to 80.") [View record](results/member-c.md#test-id-age-ep-90-c)

### Input-Format Observations

Required observations:
- Blank age.
- Non-numeric age input.

Results:
- Blank age (AGE-FMT-BLANK-D, member-d): Observation only — prevented by the browser with "Please fill out this field." [View record](results/member-d.md#test-id-age-fmt-blank-d)
- Non-numeric `abc` (AGE-FMT-ABC-D, member-d): Observation only — the browser did not allow the letters to be entered. [View record](results/member-d.md#test-id-age-fmt-abc-d)

### 2-Point Boundary Testing

Required values:
17, 18, 80, 81.

Results:
- 17 (AGE-2P-17-A, member-a): Pass — [View record](results/member-a.md#2-point-boundary-tests)
- 18 (AGE-2P-18-B, member-b): _To be added_
- 80 (AGE-2P-80-C, member-c): Pass — [View record](results/member-c.md#test-id-age-2p-80-c)
- 81 (AGE-2P-81-D, member-d): Pass — [View record](results/member-d.md#test-id-age-2p-81-d)

### 3-Point Boundary Testing

Required values:
16, 17, 18, 19, 79, 80, 81, 82.

Convention: ISTQB CTFL v4.0 eight-value convention.

Results:
- 16 (member-a): Pass — [View record](results/member-a.md#3-point-boundary-tests)
- 17: reused from AGE-2P-17-A — _To be added_
- 18: reused from AGE-2P-18-B — _To be added_
- 19 (member-b): _To be added_
- 79 (AGE-3P-79-C, member-c): Pass — [View record](results/member-c.md#test-id-age-3p-79-c)
- 80: reused from AGE-2P-80-C (member-c) — [View record](results/member-c.md#test-id-age-2p-80-c)
- 81: reused from AGE-2P-81-D (member-d) — [View record](results/member-d.md#test-id-age-2p-81-d)
- 82 (AGE-3P-82-D, member-d): Pass — [View record](results/member-d.md#test-id-age-3p-82-d)

## Member Contributions

### Member A

- Guided results: [View results](results/member-a.md)
- Self-designed tests: [View tests](exploratory/member-a.md)
- Reflection: [View reflection](reflections/member-a.md)
- Chosen investigation: Age validation and error recovery. I tested whether the form accepts a valid age after correcting an invalid age without refreshing the page.
- Main observation: I learned that negative tests can pass when invalid inputs are correctly rejected. I also learned how boundary testing helps identify validation issues near the accepted age limits
- Pull request: [View my pull request](https://github.com/Aori7/manual-testing/pull/6)

### Member B

- Guided results: [View results](results/member-b.md)
- Self-designed tests: [View tests](exploratory/member-b.md)
- Reflection: [View reflection](reflections/member-b.md)
- Chosen investigation: _To be added_
- Main observation: _To be added_
- Pull request: _To be added_

### Member C

- Guided results: [View results](results/member-c.md)
- Self-designed tests: [View tests](exploratory/member-c.md)
- Reflection: [View reflection](reflections/member-c.md)
- Chosen investigation: Surname length boundaries (10, 11, 79 and 80 characters).
- Main observation: Surnames of 11 and 79 characters were accepted, and 10 and 80 were rejected with "too short" and "too long" messages, so the range 11 to 79 is treated as inclusive. The baseline first name `Alex` was rejected as "too short" although the instructions give no minimum, which is an unanswered requirement question.
- Pull request: PASTE_YOUR_PR_LINK_HERE

### Member D

- Guided results: [View results](results/member-d.md)
- Self-designed tests: [View tests](exploratory/member-d.md)
- Reflection: [View reflection](reflections/member-d.md)
- Chosen investigation: Surname length boundaries (10, 11, 79 and 80 characters).
- Main observation: All four passed, so "between 11 and 79" is treated as inclusive. Surname errors appear as red messages on the page, while age errors are browser popup bubbles shown before submission, so the two fields are validated differently.
- Pull request: [View my pull request](https://github.com/Aori7/manual-testing/pull/4)

## Team Conclusion

- What did the guided activities help us understand?

The guided activities helped us understand how equivalence partitioning and boundary testing can be used to select test data effectively. We also learned the difference between positive and negative testing, and that a negative test can pass when the system correctly rejects invalid inputs.

- How did members extend the testing in different directions?

During the open-ended activity, each member chose an area to investigate beyond the guided tests. This allowed us to explore different aspects of the form's behaviour, such as input validation and error handling, rather than only checking whether inputs were accepted or rejected.

- What would the team investigate next?

As a team, we would investigate how the form handles errors when users correct invalid inputs. We could also test multiple invalid fields at the same time to see whether the form displays clear error messages and allows users to correct their mistakes easily.
