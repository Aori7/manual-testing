# Self-Designed Testing — Member C

## Testing Idea

Investigate the surname length boundaries on the Test Pages validation form.

## Reason

The age field has already been tested with boundary values. The surname has a stated length requirement, so it is a good place to apply the same technique to a different field.

## Test Basis

The instructions page says the surname should be between 11 and 79 characters.

Assumption: the requirement does not say whether 11 and 79 are inclusive. I am assuming they are, as I did for the age range of 18 to 80.

## Approach

Use the agreed baseline for every other field and change only the surname. Test the values on each side of both boundaries: 10, 11, 79 and 80 characters. I will count the length before each test.

## Test Cases

### Test ID: OWN-C-01

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-c |
| Status | Not run |

#### Purpose

Check that a surname one character below the minimum is rejected.

#### Preconditions

The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | `Testingstu` (10 characters) |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace the surname with `Testingstu`.
4. Submit.
5. Observe the response.

#### Expected Result

The surname is rejected because it is below the minimum of 11 characters.

#### Actual Result

After entering the surname `Testingstu` (10 characters) with the baseline values and selecting Submit, a red message "Surname provided is too short" appeared under the surname field. The form stayed on screen and no results page was shown.

#### Evidence

[View screenshot](../evidence/member-c/own-c-01.png)

---

### Test ID: OWN-C-02

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-c |
| Status | Not run |

#### Purpose

Check that a surname at the minimum length is accepted.

#### Preconditions

The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | `Testingstud` (11 characters) |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace the surname with `Testingstud`.
4. Submit.
5. Observe the response.

#### Expected Result

The surname is accepted because it is 11 characters, the minimum.

#### Actual Result

After entering the surname `Testingstud` (11 characters) with the baseline values and selecting Submit, the form submitted. The Validation Report showed "Valid Input: Your Input passed validation" and the "You submitted" list showed Surname `Testingstud`.

#### Evidence

[View screenshot](../evidence/member-c/own-c-02.png)

---

### Test ID: OWN-C-03

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-c |
| Status | Not run |

#### Purpose

Check that a surname at the maximum length is accepted.

#### Preconditions

The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | 79 letter `a` characters |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace the surname with 79 characters.
4. Submit.
5. Observe the response.

#### Expected Result

The surname is accepted because it is 79 characters, the maximum.

#### Actual Result

After pasting a 79-character surname (checked with PowerShell before pasting) with the baseline values and selecting Submit, the form submitted. The Validation Report showed "Valid Input: Your Input passed validation" and the long surname appeared under "You submitted". The screenshot cuts off the end of the surname, so the displayed length is not visible in it.

#### Evidence

[View screenshot](../evidence/member-c/own-c-03.png)

---

### Test ID: OWN-C-04

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-c |
| Status | Not run |

#### Purpose

Check that a surname one character above the maximum is rejected.

#### Preconditions

The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Surname | 80 letter `a` characters |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace the surname with 80 characters.
4. Submit.
5. Observe the response.

#### Expected Result

The surname is rejected because it is above the maximum of 79 characters.

#### Actual Result

After pasting an 80-character surname (checked with PowerShell before pasting) with the baseline values and selecting Submit, a red message "Surname provided is too long" appeared under the surname field. The form stayed on screen and no results page was shown.

#### Evidence

[View screenshot](../evidence/member-c/own-c-04.png)

---

## Overall Observations

All four surname length tests matched the expected results. Lengths 10 and 80 were rejected with messages saying the surname was too short or too long, and lengths 11 and 79 were accepted. This is consistent with the stated requirement that the surname is between 11 and 79 characters, with both ends inclusive. For the rejected values, the message appeared on the form and no results page was shown, so the check appears to happen before the data is sent to the server. I did not test whether the server also enforces the limits.

## Next Question

The first name `Alex` was rejected as "Firstname too short" although the instructions give no minimum length. What is the minimum first name length the form accepts, and is it documented anywhere?