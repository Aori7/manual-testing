# Reflection — Member C

## 1. What makes a test positive or negative?

A test is positive when it uses valid input and expects the application to accept it, and negative when it uses invalid input and expects the application to reject it. For example, age 79 was a positive test and age 90 was a negative test.

## 2. Why can a negative test pass?

A negative test passes when the application handles the invalid input correctly. In LOGIN-N02, the error "Epic sadface: Password is required" meant the test passed because the login was rejected as expected.

## 3. How did equivalence partitioning help you select data?

It let me choose one representative value from each group instead of testing many similar values. I tested age 90 to represent the group of ages above 80, and I would not have learned anything new from also testing 85 or 95.

## 4. What did boundary testing help you investigate?

It helped me check the exact edges of the valid range, where mistakes in the validation are most likely. Ages 79 and 80 confirmed the upper boundary was accepted, and the surname tests at 10, 11, 79 and 80 characters confirmed both boundaries of the surname length.

## 5. What did you choose to test during the open-ended activity, and why?

I tested the surname length boundaries (10, 11, 79 and 80 characters). The requirement for the surname was clearly stated, and it let me apply boundary testing to a different field from the age tests.

## 6. Did your observations lead to follow-up tests?

My first baseline attempt was rejected with "Firstname too short" even though the requirements give no minimum first name length. This led me to agree a new baseline with my team and to record a requirement question.

## 7. How does your Git history show your contribution?

My branch `testing/member-c` shows commits for preparing my test record, recording my login result, my age tests, my self-designed test plan and my self-designed test results. Each commit message describes what I added.