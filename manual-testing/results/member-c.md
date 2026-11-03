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

## 2-Point Boundary Tests

## 3-Point Boundary Tests