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

## 3-Point Boundary Tests