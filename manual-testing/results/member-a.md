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
| Website | Website name |
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
| Tester | Your member identifier |
| Website | Website name |
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

[View screenshot](../evidence/member-a/login-r01.png)

---

## Equivalence Partitioning

## 2-Point Boundary Tests

## 3-Point Boundary Tests