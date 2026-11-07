# Manual Testing Results — Member B

## Environment

| Item | Details |
|---|---|
| Tester identifier | member-b |
| Date and time | 3/11/26 9:30am |
| Browser and version | firefox |
| Operating system | windows 11 |

## Login Tests
### Test ID: LOGIN-N01

| Item | Details |
|---|---|
| Test type | Negative |
| Tester | member b |
| Website | Swag Labs |
| Status | pass |

#### Purpose

What does this test check?
This test checks that whether the login is rejected when an incorrect password is used to login.

#### Preconditions

What must be true before the test starts?
The user must be logged out

#### Test Data

| Field | Value |
|---|---|
| Input username | standard_user |
| input password | wrong_password |

#### Steps

1. follow the shared starting procedure
2. enter a valid username
3. enter the incorrect password
4. select login
5. observe the page and feedback

#### Expected Result

Write this before executing the test.
the login should be rejected as expected

#### Actual Result

the login rejection occured as expected

#### Evidence

[View screenshot](../evidence/member-b/login-n01.png)
---

## Equivalence Partitioning
### Test ID: AGE-EP-10-B

| Item | Details |
|---|---|
| Test type | negative |
| Tester | member b |
| Website | test pages |
| Status | pass |

#### Purpose

What does this test check?
this test checks the age validation

#### Preconditions

What must be true before the test starts?
when testing age, every other field should be valid and unchanged

#### Test Data

| Field | Value |
|---|---|
| Firstname | Alexander|
| Lastname  | TestingStudent |
| Age | 10 |
| Country | Singapore | 
| Notes | Manual testing classroom exercise |

#### Steps
 
1. restore the form
2. enter the valid baseline
3. change only age
4. write the expected result
5. submit
6. observe acceptance or rejection
7. where displayed, verify the submitted age
8. record the actual result and status in a seperate test-case block

#### Expected Result

Write this before executing the test.
the test rejects the age value

#### Actual Result

the test rejects meaning a validation error is returned for the age

#### Evidence

[View screenshot](../evidence/member-b/AGE-EP-10-B.png)

---

## 2-Point Boundary Tests

## 3-Point Boundary Tests