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
| Status | Pass |

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

With all other fields set to the agreed baseline and Surname set to `Surnameabc` (10 characters), I selected Submit. The submission was rejected: a red message appeared on the page directly below the Last name field reading "Surname provided is too short". The entered values remained in the form.

Observation: unlike the age tests, this was not a browser popup bubble. It was a message displayed in the page itself, so surname length appears to be checked differently from age. From the browser alone I could not confirm whether this message came from the server or from the page's own script.

#### Evidence

[View screenshot](../evidence/member-d/own-01.png)

---

### Test ID: OWN-D-02

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Pass |

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

With all other fields set to the agreed baseline and Surname set to `Surnameabcd` (11 characters), I selected Submit. No error appeared on the Last name field. A "Validation Report" section appeared below the form stating "Valid Input — Your Input passed validation", followed by a "You submitted" list showing Firstname `Alexander`, Surname `Surnameabcd`, Age `30`, Country `Singapore`, and Notes `Manual testing classroom exercise`.

The submitted surname matched the intended 11-character value, so the minimum length of 11 was accepted. Together with OWN-D-01, this shows the transition from invalid (10) to valid (11) is in the expected place.

#### Evidence

[View screenshot](../evidence/member-d/own-02.png)

---

### Test ID: OWN-D-03

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Pass |

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

With all other fields set to the agreed baseline and Surname set to the 79-character test value, I selected Submit. A "Validation Report" appeared stating "Valid Input — Your Input passed validation". The "You submitted" list showed the full surname ending in `...klmnopqrst`, so the value was not truncated. The maximum length of 79 was accepted.

Note: my first attempt was invalid because the form had been reloaded without the baseline (First name empty, Country "Afghanistan", Notes empty). The browser stopped it with "Please fill out this field." on First name. I did not count that attempt and repeated the test with the full baseline.

#### Evidence

[View screenshot](../evidence/member-d/own-03.png)

---

### Test ID: OWN-D-04

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Pass |

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

With all other fields set to the agreed baseline and Surname set to the 80-character test value, I selected Submit. The submission was rejected: a red message appeared on the page directly below the Last name field reading "Surname provided is too long". No Validation Report appeared.

The field did not stop me entering the 80th character. The whole value could be pasted in, and the length was only rejected when I submitted.

#### Evidence

[View screenshot](../evidence/member-d/own-04.png)

---

## Overall Observations

All four surname boundary tests passed. Lengths 10 and 80 were rejected; 11 and 79 were accepted. This shows that "between 11 and 79" is treated as inclusive, which answers my requirement question for this form.

Surname length is validated differently from age. Age errors appeared as browser popup bubbles before submission. Surname errors appeared as red messages written on the page. The surname field also did not limit how many characters could be typed. From the browser alone I could not confirm whether the surname messages came from the server or the page's own script.

## Next Question

Does the First name field (required, fewer than 90 characters) behave the same way as Surname? I would test lengths 89 and 90 to see whether "fewer than 90" means 89 is the maximum.