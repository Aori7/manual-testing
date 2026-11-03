# Self-Designed Testing — Member D

## Testing Idea

Apply equivalence partitioning and 2-point boundary testing to the **Surname (Last name)** length on the Test Pages validation form.

## Reason

The guided activities only tested age. Surname has its own length rule, so it has its own boundaries where an off-by-one mistake could happen (e.g. `length > 11` instead of `length >= 11`).

During the guided age tests, every rejection came from browser (client-side) validation. I also want to see whether surname length is checked by the browser in the same way, or whether it reaches the server.

## Test Basis

Published requirement (as listed in the practical README): Surname must be between 11 and 79 characters.

Assumptions and unclear requirements:

- Assumption: "between 11 and 79" is inclusive, so lengths 11 to 79 are valid. The requirement does not say this explicitly. Requirement question: are 11 and 79 themselves valid?
- Assumption: length counts every character, and the test data contains only letters (no spaces), so there is no question about trimming.
- All other fields use the agreed team baseline: First name `Alexander`, Age `30`, Country `Singapore`, Notes `Manual testing classroom exercise`.

## Approach

Partitions for surname length (whole characters):

| Partition | Length | Test type | Expected |
|---|---|---|---|
| Too short | 0–10 | Negative | Reject |
| Valid | 11–79 | Positive | Accept |
| Too long | 80+ | Negative | Reject |

2-point boundary values: **10, 11, 79, 80**.

The baseline surname `TestingStudent` (14 characters) already covers the valid partition, so I focus on the boundaries.

Test strings were prepared with exact lengths, starting with `Surname` followed by the alphabet, so the length can be checked by counting.

## Test Cases

### Test ID: OWN-D-01

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Not run |

#### Purpose

Check that a surname of 10 characters (one below the minimum) is rejected.

#### Preconditions

The validation form is open and reloaded. All other fields use the agreed baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | `Surnameabc` (10 characters) |
| Other fields | Agreed baseline, Age `30` |

#### Steps

1. Reload the validation form.
2. Enter the agreed baseline with Age `30`.
3. Replace the surname with the test value.
4. Submit.
5. Record whether the browser blocks it or the server responds, and the exact feedback.

#### Expected Result

Rejected, because 10 characters is below the minimum of 11.

#### Actual Result

Not recorded — test has not been executed.

#### Evidence

Not captured.

---

### Test ID: OWN-D-02

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Not run |

#### Purpose

Check that a surname of exactly 11 characters (the minimum) is accepted.

#### Preconditions

The validation form is open and reloaded. All other fields use the agreed baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | `Surnameabcd` (11 characters) |
| Other fields | Agreed baseline, Age `30` |

#### Steps

1. Reload the validation form.
2. Enter the agreed baseline with Age `30`.
3. Replace the surname with the test value.
4. Submit.
5. Record the response and, if shown, check the submitted surname.

#### Expected Result

Accepted, assuming 11 is inclusive in "between 11 and 79".

#### Actual Result

Not recorded — test has not been executed.

#### Evidence

Not captured.

---

### Test ID: OWN-D-03

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Not run |

#### Purpose

Check that a surname of exactly 79 characters (the maximum) is accepted.

#### Preconditions

The validation form is open and reloaded. All other fields use the agreed baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | `Surnameabcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrst` (79 characters) |
| Other fields | Agreed baseline, Age `30` |

#### Steps

1. Reload the validation form.
2. Enter the agreed baseline with Age `30`.
3. Paste the test value into the surname field.
4. Check that the whole value was entered (it was not cut off).
5. Submit.
6. Record the response and, if shown, check the submitted surname.

#### Expected Result

Accepted, assuming 79 is inclusive in "between 11 and 79".

#### Actual Result

Not recorded — test has not been executed.

#### Evidence

Not captured.

---

### Test ID: OWN-D-04

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Not run |

#### Purpose

Check that a surname of 80 characters (one above the maximum) is rejected.

#### Preconditions

The validation form is open and reloaded. All other fields use the agreed baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | `Surnameabcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstu` (80 characters) |
| Other fields | Agreed baseline, Age `30` |

#### Steps

1. Reload the validation form.
2. Enter the agreed baseline with Age `30`.
3. Paste the test value into the surname field.
4. Check whether all 80 characters were entered, or whether the field stopped accepting characters.
5. Submit.
6. Record the response and the exact feedback.

#### Expected Result

Rejected, because 80 characters is above the maximum of 79. This could happen by the field refusing the 80th character, a browser popup, or a server error.

#### Actual Result

Not recorded — test has not been executed.

#### Evidence

Not captured.

---

## Overall Observations

To be completed after execution.

## Next Question

To be completed after execution.
