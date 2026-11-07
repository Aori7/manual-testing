# Reflection — Member D

## 1. What makes a test positive or negative?

A test is positive when it uses valid input, like an 11-character surname, and negative when it uses invalid input, like an 80-character surname or a missing username. It depends on the input, not on whether the test passes or fails.

## 2. Why can a negative test pass?

A negative test passes when the system correctly rejects the invalid input. For example, in LOGIN-N03 the error "Username is required" appeared, which was the expected behaviour, so the test passed.

## 3. How did equivalence partitioning help you select data?

It let me split age into three groups (below 18, 18–80, above 80) and pick one value from each instead of testing lots of random numbers. This made sure every group was covered with only a few tests.

## 4. What did boundary testing help you investigate?

It helped me check the exact points where input changes from valid to invalid, such as age 80 and 81, or surname lengths 10 and 11. These are where mistakes like using `>` instead of `>=` would show up, which a middle value like 30 would not reveal.

## 5. What did you choose to test during the open-ended activity, and why?

I tested surname length boundaries (10, 11, 79 and 80 characters) because surname has its own length rule that the guided activities didn't cover. It also let me apply boundary testing to a text field and check whether "between 11 and 79" was inclusive.

## 6. Did your observations lead to follow-up tests?

Yes. I noticed surname errors appeared as red messages on the page, while age errors were browser popups, so the fields are validated differently. This made me want to test first name length (89 and 90 characters) next to see if it behaves like surname.

## 7. How does your Git history show your contribution?

I worked on my own branch, `testing/member-d`, and committed after each stage: preparing my record, login testing, input-format observations, boundary tests, planning my own tests, and recording their results. Each commit shows what I tested at that point, so the history shows my progress through the practical.