# Manual Testing Results — Member D

## Environment

| Item | Details |
|---|---|
| Tester identifier | member-d |
| Date and time | 3 Nov 2026, 17:00 SGT |
| Browser and version | Google Chrome 142.0.7444.60 |
| Operating system | Windows 11 Home 24H2 |

## Login Tests

### Test ID: LOGIN-N03

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | SauceDemo |
| Status | Pass |

#### Purpose

Check that a login attempt with a missing username is rejected.

#### Preconditions

The SauceDemo login page is open.
The user is logged out and both input fields are empty.

#### Test Data

| Field | Value |
|---|---|
| Username | Empty |
| Password | `secret_sauce` |

#### Steps

1. Open the login page.
2. Log out if already logged in.
3. Clear both input fields and confirm the logged-out state.
4. Leave the username empty.
5. Enter the password `secret_sauce`.
6. Select `Login`.
7. Observe the feedback and the page shown.

#### Expected Result

The login attempt is rejected and validation feedback appears. The inventory page is not reached.

#### Actual Result

After selecting Login with the username empty and the password `secret_sauce`, the page stayed on the Swag Labs login page. A red error banner appeared with the message "Epic sadface: Username is required". Both input fields were outlined in red with an error icon. The inventory page was not reached.

#### Evidence

[View screenshot](../evidence/member-d/login-n03.png)

---

## Equivalence Partitioning — Input-Format Observations

> Four-member team: Member D performs both input-format observations.
> These are separate from the three numeric partitions (10, 30, 90).
> The requirements do not clearly define the expected behaviour for blank or non-numeric age, so these are recorded as observations.

### Test ID: AGE-FMT-BLANK-D

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | Input-format observation |
| Status | Observation only |

#### Purpose

Observe how the form handles a blank age when all other fields are valid.

#### Preconditions

The validation form is open.
All other fields will use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Age | Empty |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Clear the age field so it is empty.
4. Submit.
5. Record whether submission is prevented in the browser or rejected after submission, and what feedback appears.

#### Expected Result

Requirement question: the published requirements state that age must be between 18 and 80 but do not say whether age is required or how a blank age is handled. My assumption is that a blank age will not be accepted as a valid submission.

#### Actual Result

With all other fields set to the agreed baseline and Age left empty, I selected Submit. The form was not submitted. The browser showed a validation popup on the Age field with the message "Please fill out this field." and the page did not change.

- Can the field be left blank? Yes, the field can be empty, but the form cannot be submitted with it empty.
- Prevented or rejected? Prevented by client-side (browser) validation before submission. No server response was received, so this does not show how the server handles a blank age.
- Feedback: Browser popup "Please fill out this field." next to the Age field.

Additional observation: the Age field shows up/down spinner arrows, suggesting it is a number input.

Requirement question: the browser treats Age as required, but the published requirements only state the 18–80 range. Is Age intended to be a required field?

Record:
- Can the field be left blank?
- Is submission prevented by the browser, or rejected after submission?
- What feedback appears?

#### Evidence

[View screenshot](../evidence/member-d/age-fmt-blank.png)

---

### Test ID: AGE-FMT-ABC-D

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | Input-format observation |
| Status | Observation only |

#### Purpose

Observe how the form handles non-numeric age input.

#### Preconditions

The validation form is open.
All other fields will use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Age | `abc` |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Clear the age field and try to type `abc`.
4. Note whether the characters appear in the field.
5. If they appear, submit.
6. Record what happens and what feedback appears.

#### Expected Result

Requirement question: the requirements do not state how non-numeric age input is handled. My assumption is that `abc` will not be accepted as a valid age, either because the browser prevents it from being entered or because it is rejected.

#### Actual Result

With all other fields set to the agreed baseline, I clicked into the Age field and tried to type `abc`. The characters did not appear; the Age field stayed empty. Because the input could not be entered, the form was not submitted with `abc`.

- Could `abc` be typed into the field? No. The browser prevented the letters from being entered.
- Prevented, cleared, or rejected? Prevented at input by the browser (number field). It was never submitted, so this does not show how the server would handle non-numeric age.
- Feedback: No message appeared; the letters simply did not register.

Requirement question: the requirements do not state how non-numeric age should be handled. Server-side handling of non-numeric age could not be observed through normal browser use.

Record:
- Could `abc` be typed into the field?
- Was it prevented, cleared, or rejected?
- What feedback appears?

Note: if the browser prevents the input, record that. Do not describe it as a server rejection.

#### Evidence

[View screenshot](../evidence/member-d/age-fmt-abc.png) — Age field still empty after attempting to type `abc`.

---

## 2-Point Boundary Tests

### Test ID: AGE-2P-81-D

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Pass |

#### Purpose

Check that an age immediately above the maximum is rejected.

#### Preconditions

The validation form is open.
All other fields will use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Age | `81` |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace age with `81`.
4. Submit.
5. Observe the response.

#### Expected Result

Age 81 is rejected because it is above the maximum age of 80.

#### Actual Result

With all other fields set to the agreed baseline and Age set to `81`, I selected Submit. The form was not submitted. The browser showed a validation popup on the Age field with the message "Value must be less than or equal to 80." and the page did not change.

Age 81 was rejected by client-side (browser) validation before submission, so no server response was observed.

#### Evidence

[View screenshot](../evidence/member-d/age-2p-81.png)

---

## 3-Point Boundary Tests

> Convention: ISTQB CTFL v4.0 eight-value convention (16, 17, 18, 19, 79, 80, 81, 82).

### Test ID: AGE-3P-82-D

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-d |
| Website | Test Pages validation form |
| Technique | 3-point boundary testing |
| Status | Pass |

#### Purpose

Check that an age one above the invalid boundary value 81 is rejected.

#### Preconditions

The validation form is open.
All other fields will use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Age | `82` |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace age with `82`.
4. Submit.
5. Observe the response.

#### Expected Result

Age 82 is rejected because it is above the maximum age of 80.

#### Actual Result

With all other fields set to the agreed baseline and Age set to `82`, I selected Submit. The form was not submitted. The browser showed a validation popup on the Age field with the message "Value must be less than or equal to 80." and the page did not change.

Age 82 was rejected by client-side (browser) validation before submission, so no server response was observed.

#### Evidence

[View screenshot](../evidence/member-d/age-3p-82.png)

---

### Age 81 — Reused Execution

- Original test: `AGE-2P-81-D`
- Tester: `member-d`
- Record: [AGE-2P-81-D above](#test-id-age-2p-81-d)
- Reason for reuse: The baseline, environment, and procedure remain applicable.
