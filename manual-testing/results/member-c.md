# Manual Testing Results — Member C

## Environment

| Item | Details |
|---|---|
| Tester identifier | member-c |
| Date and time | 3/11/2026 10.00am |
| Browser and version | Opera GX 154.0.8037.99 |
| Operating system | Windows 11 |

## Login Tests
### Test ID: LOGIN-N02

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-c |
| Website | SauceDemo |
| Status | Not run |

#### Purpose

Check that login is rejected when the password is missing.

#### Preconditions

The SauceDemo login page is open and I am logged out. Both fields are empty.

#### Test Data

| Field | Value |
|---|---|
| Username | `standard_user` |
| Password | Empty |

#### Steps

1. Open https://www.saucedemo.com/ and confirm you are logged out.
2. Clear both input fields.
3. Enter `standard_user` in the username field.
4. Leave the password field empty.
5. Select Login.
6. Observe the page and any feedback.

#### Expected Result

The attempt is rejected with validation feedback. The inventory page is not reached.

#### Actual Result

After entering `standard_user` with an empty password field and selecting Login, the login was rejected. The page stayed on the login screen. A red error banner appeared with the message "Epic sadface: Password is required". The password field was highlighted in red and both input fields showed a red X icon. The inventory page was not reached.

#### Evidence

[View screenshot](../evidence/member-c/login-n02.png)
---
## Equivalence Partitioning
### Test ID: AGE-EP-90-C

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member-c |
| Website | Test Pages validation form |
| Technique | Equivalence partitioning |
| Status | Not run |

#### Purpose

Check that an age above the accepted range (EP-03) is rejected.

#### Preconditions

The validation form is open and all other fields use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| First name | `Alexander` |
| Surname | `TestingStudent` |
| Age | `90` |
| Country | Singapore |
| Notes | `Manual testing classroom exercise` |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline values.
3. Replace age with `90`.
4. Submit the form.
5. Observe whether the submission succeeds or a validation error appears.

#### Expected Result

Age 90 is rejected because it is above the maximum age of 80.

#### Actual Result

After entering the baseline values with age changed to `90` and selecting Submit, the form did not submit. A browser validation tooltip appeared on the age field with the message "Value must be less than or equal to 80." The age field was highlighted and no results page was shown. The rejection came from client-side (browser) validation, so no server response was observed for this value.

#### Evidence

[View screenshot](../evidence/member-c/age-ep-90-c.png)

---
## 2-Point Boundary Tests
### Test ID: AGE-2P-80-C

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-c |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Not run |

#### Purpose

Check that the maximum valid age is accepted.

#### Preconditions

The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| First name | `Alexander` |
| Surname | `TestingStudent` |
| Age | `80` |
| Country | Singapore |
| Notes | `Manual testing classroom exercise` |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace age with `80`.
4. Submit the form.
5. Observe whether the submission succeeds.

#### Expected Result

Age 80 is accepted because it is the maximum valid age. The form submits successfully and the results page shows age 80.

#### Actual Result

After entering the baseline values with age changed to `80` and selecting Submit, the form submitted and a results page appeared. The Validation Report showed "Valid Input: Your Input passed validation". The "You submitted" list showed Firstname `Alexander`, Surname `TestingStudent`, Age `80`, Country `Singapore` and Notes `Manual testing classroom exercise`. No validation errors were shown.

#### Evidence

[View screenshot](../evidence/member-c/age-2p-80-c.png)

---
## 3-Point Boundary Tests
### Test ID: AGE-3P-79-C

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member-c |
| Website | Test Pages validation form |
| Technique | 3-point boundary testing |
| Status | Not run |

#### Purpose

Check that age 79, one below the maximum boundary value of 80, is accepted.

#### Preconditions

The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| First name | `Alexander` |
| Surname | `TestingStudent` |
| Age | `79` |
| Country | Singapore |
| Notes | `Manual testing classroom exercise` |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace age with `79`.
4. Submit the form.
5. Observe whether the submission succeeds.

#### Expected Result

Age 79 is accepted because it is within the valid range of 18 to 80. The form submits successfully and the results page shows age 79.

#### Actual Result

After entering the baseline values with age changed to `79` and selecting Submit, the form submitted and a results page appeared. The Validation Report showed "Valid Input: Your Input passed validation". The "You submitted" list showed Firstname `Alexander`, Surname `TestingStudent`, Age `79`, Country `Singapore` and Notes `Manual testing classroom exercise`. No validation errors were shown.

#### Evidence

[View screenshot](../evidence/member-c/age-3p-79-c.png)

---