# Manual Testing Results — Member A

## Environment

| Item | Details |
|---|---|
| Tester identifier | member-a |
| Date and time | 3/11/2026, 0939|
| Browser and version | google chrome |
| Operating system | windows |

## Login Tests
### Test ID: LOGIN-P01

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member a |
| Website | Swag Labs |
| Status | Pass |

#### Purpose

This test checks if the user is brought to the inventory page after entering the correct username and password

#### Preconditions

The user must be logged out.

#### Test Data

| Field | Value |
|---|---|
| Username | standard_user |
| Password | secret_sauce |

#### Steps

1. Follow the shared starting procedure.
2. Enter the username.
3. Enter the password.
4. Select Login.
5. Observe the page reached.
6. Check that products are visible.

#### Expected Result

The inventory page appears and products are visible.

#### Actual Result

After entering the username and password and selecting the login button, the inventory page appeared and
the product list was visible.

#### Evidence
[View screenshot](../evidence/member-a/login-p01.png)

---

### Test ID: LOGIN-R01

| Item | Details |
|---|---|
| Test type | Recovery |
| Tester | memeber a |
| Website | Swag Labs |
| Status | pass |

#### Purpose

This test checks if the user is brought to the inventory page after 1 failed and 1 valid attempt at logging in

#### Preconditions

The user must be logged out

#### Test Data

| Field | Value |
|---|---|
| Username | standard_user |
| Incorrect Password | wrong_password |
| Correct Password | secret_sauce |

#### Steps

1. Follow the shared starting procedure.
2. Enter standard_user and wrong_password.
3. Select Login.
4. Confirm rejection.
5. Replace the password with secret_sauce.
6. Keep the username unchanged.
7. Select Login again.
8. Check whether the inventory appears.

#### Expected Result

The invalid attempt is rejected. After correcting the password, login succeeds.
Record both stages in the actual result.

#### Actual Result

After entering the incorrect password, it remains on the login page and displays a rejection message.
After confirming the rejection and entering the correct passowrd, it displays the inventory page.

#### Evidence

[View screenshot](../evidence/member-a/login-r01-p1.png)
[View screenshot](../evidence/member-a/login-r01-p2.png)

---

## Equivalence Partitioning
### Test ID: AGE-EP-30-A

| Item | Details |
|---|---|
| Test type | Positive |
| Tester | member a |
| Website | Test Pages |
| Status | Pass |

#### Purpose

To verify that the form accepts a valid age of 30, which falls within the required age range of 18–80

#### Preconditions

All other input fields contain valid baseline values. Only the age field is changed

#### Test Data

| Field | Value |
|---|---|
| First Name | Alex |
| Surname | TestingStudent |
| Age | 30 |
| Country | Singapore |
| Notes | Manual testing classroom exercise |

#### Steps

1. Enter the test data values into the input fields.
2. Click the Submit button and observe the result.

#### Expected Result

The form should accept Age 30 and submit successfully without displaying any age validation errors.

#### Actual Result

The form accepted Age 30 and submitted successfully without any validation errors.

#### Evidence

[View screenshot](../evidence/member-a/AGE-EP-30-A.png)

---

## 2-Point Boundary Tests
### Test ID: AGE-2P-17-A

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member a |
| Website | Test Pages validation form |
| Technique | 2-point boundary testing |
| Status | Not run |

#### Purpose

Check that an age immediately below the minimum is rejected.

#### Preconditions

The validation form is open.
All other fields will use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Age | `17` |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace age with `17`.
4. Submit.
5. Observe the response.

#### Expected Result

Age 17 is rejected because it is below the minimum age of 18.

#### Actual Result

A validation error messgae appears under the age field, asking for an input equal or greater than 18.

#### Evidence

[View screenshot](../evidence/member-a/AGE-2P-17-A.png)

---

## 3-Point Boundary Tests