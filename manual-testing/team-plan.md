# Team Plan

## Team Identifier

## Members

### Member A
- GitHub username: RuiMin8
- Coordination responsibility: Team Coordination

### Member B
- GitHub username: Aori7
- Coordination responsibility: Requirements and Baseline

### Member C
- GitHub username: Chris-JKSH
- Coordination responsibility: Guided Test Coverage

### Member D
- GitHub username: Lim-ZiYing
- Coordination responsibility: Evidence Organisation

## Guided Test Allocation
Four-member team: Member A also performs LOGIN-R01, and Member D performs both input-format observations.

| Activity | Member A | Member B | Member C | Member D |
|---|---|---|---|---|
| Login | LOGIN-P01, LOGIN-R01 | LOGIN-N01 | LOGIN-N02 | LOGIN-N03 |
| Equivalence partitioning | Age 30 | Age 10 | Age 90 | Blank age, `abc` |
| 2-point boundaries | 17 | 18 | 80 | 81 |
| 3-point boundaries | 16 | 19 | 79 | 82 |
## Agreed Baseline Data
Activity 2
Firstname: Alexander
Last Name: TestingStudent
Age: Assigned testing age
Country: Singapore
Notes: Manual testing classroom exercise

## Open-Ended Testing Allocation

### Member D — Open-Ended Testing

- Chosen area: Surname length on the Test Pages validation form.
- Question to investigate: Are surname lengths 10, 11, 79 and 80 handled correctly, and is "between 11 and 79" inclusive?

Members A, B and C: to be added.
## Repository Integration Arrangements
- Members A and D share repository integration (four-member team).
- Each member works on `testing/member-x` and merges through their own pull request.
- Merge method: "Create a merge commit", to preserve individual commits.
- Evidence is saved in `evidence/member-x/`, with filenames based on the test ID in lowercase (e.g. `login-n03.png`).