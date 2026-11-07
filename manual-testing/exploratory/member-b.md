# Self-Designed Testing — Member A

## Testing Idea

What do I want to investigate?
investigate decimal age input validation in the test pages validation form.
determine whether the form accepts decimal age values and how it handles decimal values outside the permitted age range of 18-80

## Reason

Why is this worth testing?
previous activities tested whole-number ages using equivalnce partitioning and boundary value analysis
however, decimal age values have not been explicitly tested. investigating these inputs may reveal how the form handles unexpected or unspecified input formats

## Test Basis

What requirement or stated expectation am I checking?
the agreed age requirement is 18-80 inclusive.
the requirement does not explicitly state whether decimal age values are allowed.

Record any assumptions or unclear requirements.
if the form accepts numeraical ages, values below 18 or above 80 should be rejected.

## Approach

How will I choose data and perform the tests?
test 3 decimal values:
1. 18.5 to investigate within the valid range.
2. 17.5 to investigate decimaal input below the maximum range
3. 80.5 to investigate decimal input above the maximum age

## Test Cases

### Test ID: OWN-B-01

| Item | Details |
|---|---|
| Test type | Exploratory |
| Tester | member-b |
| Status | pass |

#### Purpose

What does this individual test check?
Investigate whether the form accepts a decimal age of 18.5, which falls within the numerical range of 18–80.

#### Preconditions

What starting state is required?
The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

List the exact inputs or actions.
Firstname: Alexander
Last Name: TestingStudent
Age: 18.5
Country: Singapore
Notes: Manual testing classroom exercise

#### Steps

1. Restore the validation fform
2. Enter the agreed baseline data
3. enter 18.5 as the age
4. submit the form
5. observe the response

#### Expected Result

State the expected behaviour and its basis.
The age is numerically within the permitted range. However, whether decimal values are accepted is unspecified.

If the behaviour is unspecified, record the question being investigated.
Record whether the form accepts or rejects the input.

#### Actual Result

The form rejects the input

#### Evidence

[View screenshot](../evidence/member-b/OWN-B-01.png)

---

### Test ID: OWN-B-02

| Item | Details |
|---|---|
| Test type | Exploratory |
| Tester | member-b |
| Status | pass |

#### Purpose

What does this individual test check?
Investigate how the form handles a decimal age of 17.5, which is below the minimum permitted age of 18.

#### Preconditions

What starting state is required?
The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

List the exact inputs or actions.
Firstname: Alexander
Last Name: TestingStudent
Age: 17.5
Country: Singapore
Notes: Manual testing classroom exercise

#### Steps

1. Restore the validation fform
2. Enter the agreed baseline data
3. enter 17.5 as the age
4. submit the form
5. observe the response

#### Expected Result

State the expected behaviour and its basis.
Age 17.5 is below the minimum age of 18 and should be rejected if the numerical age-range requirement applies to decimal values.

If the behaviour is unspecified, record the question being investigated.
Record the actual behaviour.

#### Actual Result

The form rejects the input

#### Evidence

[View screenshot](../evidence/member-b/OWN-B-02.png)

---
### Test ID: OWN-B-03

| Item | Details |
|---|---|
| Test type | Exploratory |
| Tester | member-b |
| Status | pass |

#### Purpose

What does this individual test check?
Investigate how the form handles a decimal age of 80.5, which exceeds the maximum permitted age of 80.

#### Preconditions

What starting state is required?
The validation form is open. All other fields use the agreed valid baseline.

#### Test Data

List the exact inputs or actions.
Firstname: Alexander
Last Name: TestingStudent
Age: 80.5
Country: Singapore
Notes: Manual testing classroom exercise

#### Steps

1. Restore the validation fform
2. Enter the agreed baseline data
3. enter 80.5 as the age
4. submit the form
5. observe the response

#### Expected Result

State the expected behaviour and its basis.
Age 80.5 exceeds the maximum age of 80 and should be rejected if the numerical age-range requirement applies to decimal values.

If the behaviour is unspecified, record the question being investigated.
Record the actual behaviour.

#### Actual Result

The form rejects the input

#### Evidence

[View screenshot](../evidence/member-b/OWN-B-03.png)

---

## Overall Observations

What did the tests show?
All three decimal age inputs (18.5, 17.5 and 80.5) were rejected by the validation form.

The form did not accept decimal age values, regardless of whether they were within or outside the permitted age range of 18–80.

The results suggest that the form may only accept whole-number age inputs.

However, the stated requirements do not explicitly specify whether decimal values are allowed. Therefore, it is unclear whether rejecting 18.5 is intended behaviour or a limitation of the form's validation.

No unexpected differences were observed between the three test executions.

## Next Question

Does the validation form explicitly restrict age input to whole numbers, or should decimal values be supported?