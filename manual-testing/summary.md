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
- Valid credentials (LOGIN-P01, member-a): _To be added_
- Incorrect password (LOGIN-N01, member-b): _To be added_
- Missing password (LOGIN-N02, member-c): _To be added_
- Missing username (LOGIN-N03, member-d): Pass — [View record](results/member-d.md#test-id-login-n03)
- Recovery after an invalid attempt (LOGIN-R01, member-a): _To be added_

### Equivalence Partitioning

Required coverage:
- Age below the accepted range.
- Age within the accepted range.
- Age above the accepted range.

Results:
- Age 10 (AGE-EP-10-B, member-b): _To be added_
- Age 30 (AGE-EP-30-A, member-a): _To be added_
- Age 90 (AGE-EP-90-C, member-c): _To be added_

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
- 17 (AGE-2P-17-A, member-a): _To be added_
- 18 (AGE-2P-18-B, member-b): _To be added_
- 80 (AGE-2P-80-C, member-c): _To be added_
- 81 (AGE-2P-81-D, member-d): Pass — [View record](results/member-d.md#test-id-age-2p-81-d)

### 3-Point Boundary Testing

Required values:
16, 17, 18, 19, 79, 80, 81, 82.

Convention: ISTQB CTFL v4.0 eight-value convention.

Results:
- 16 (member-a): _To be added_
- 17: reused from AGE-2P-17-A — _To be added_
- 18: reused from AGE-2P-18-B — _To be added_
- 19 (member-b): _To be added_
- 79 (member-c): _To be added_
- 80: reused from AGE-2P-80-C — _To be added_
- 81: reused from AGE-2P-81-D (member-d) — [View record](results/member-d.md#test-id-age-2p-81-d)
- 82 (AGE-3P-82-D, member-d): Pass — [View record](results/member-d.md#test-id-age-3p-82-d)

## Member Contributions

### Member A

- Guided results: [View results](results/member-a.md)
- Self-designed tests: [View tests](exploratory/member-a.md)
- Reflection: [View reflection](reflections/member-a.md)
- Chosen investigation: _To be added_
- Main observation: _To be added_
- Pull request: _To be added_

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
- Chosen investigation: _To be added_
- Main observation: _To be added_
- Pull request: _To be added_

### Member D

- Guided results: [View results](results/member-d.md)
- Self-designed tests: [View tests](exploratory/member-d.md)
- Reflection: [View reflection](reflections/member-d.md)
- Chosen investigation: Surname length boundaries (10, 11, 79 and 80 characters).
- Main observation: All four passed, so "between 11 and 79" is treated as inclusive. Surname errors appear as red messages on the page, while age errors are browser popup bubbles shown before submission, so the two fields are validated differently.
- Pull request: PASTE_YOUR_PR_LINK_HERE

## Team Conclusion

_To be added once all members' work is merged._

- What did the guided activities help us understand?
- How did members extend the testing in different directions?
- What would the team investigate next?
