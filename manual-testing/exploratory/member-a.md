# Self-Designed Testing — Member A

## Testing Idea

Investigate whether the form accepts a valid age after the user enters an invalid age and corrects it.

## Reason

This is worth testing because users may accidentally enter an invalid age. The form should allow them to correct their input and submit successfully.

## Test Basis

Check if the form accepts only ages betweeen 18 to 80 inclusive.

The test checks whether the form rejects an invalid age and allows the user to correct the input in the same form

Assumption: The form should allow users to correct invalid inputs and resubmit the form.

## Approach

I will use the agreed baseline values and only change the Age field.
I will input an invalid age, 17, and submit the form. Afterwards, I will change the age to 30 and resubmit the same form.

## Test Cases

### Test ID: OWN-A-01

| Item | Details |
|---|---|
| Test type | Recovery |
| Tester | member-a |
| Status | Pass |

#### Purpose

To verify that the form allows users to correct an invalid age and submit successfully.

#### Preconditions

The validation form is open.
All other fields will use the agreed valid baseline.

#### Test Data

| Field | Value |
|---|---|
| Incorrect Age | `17` |
| Correct Age | `30` |
| Other fields | Agreed valid baseline |

#### Steps

1. Restore the validation form.
2. Enter the agreed baseline.
3. Replace age with `17`.
4. Submit.
5. Observe the response.
6. Replace age with `30`.
7. Submit.
8. Observe the response.

#### Expected Result

The form should reject Age 17 because it is below the minimum accepted age of 18. After changing the age to 30, the form should accept the corrected input and submit successfully.

#### Actual Result

A validation error messgae appears under the age field, asking for an input equal or greater than 18.
The age is changed to 30 within the same form.
The form accepted Age 30 and submitted successfully without any validation errors.

#### Evidence

[View screenshot](../evidence/member-a/OWN-A-01-p1.png)
[View screenshot](../evidence/member-a/OWN-A-01-p2.png)
[View screenshot](../evidence/member-a/OWN-A-01-p4.png)

---

## Overall Observations

The form correctly rejected Age 17 and displayed a validation error message. After changing the age to 30, I was able to submit the form successfully without refreshing the page. This shows that the form allows users to recover from invalid inputs by correcting their mistakes.

## Next Question

What would happen if the page is refreshed after entering an invalid input?