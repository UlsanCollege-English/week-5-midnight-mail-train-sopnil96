# Week 5 — Midnight Mail Train

## Summary
This assignment implements a doubly linked list to model a train made of cars,
where cars can be added to the end or detached from the rear. It also includes
utility functions to validate ticket codes using string patterns, count
priority labels recursively, and clean radio messages by removing spaces
recursively. The stretch goal provides iterative alternatives to the recursive
functions to compare both approaches.

## Approach
- **Problem 1 (MidnightMailDLL):** Built a doubly linked list with `append_car`
  to add nodes at the tail, `detach_last_car` to remove and return the tail
  node's ID, and `to_reverse_list` to traverse from tail to head.
- **Problem 2 (is_valid_ticket_code):** Used `str.startswith` to check the
  `MM-` prefix and verified the remaining 4 characters are all digits.
- **Problem 3 (count_priority_labels):** Recursively checks the first element
  against the target and adds 1 or 0, then recurses on the remaining list.
- **Problem 4 (clean_radio_message):** Recursively skips spaces and builds a
  new string character by character until the base case (empty string) is hit.

## Complexity

**`append_car`**
- Time: O(1) — direct tail access, no traversal needed.
- Space: O(1) — only one new node is created.

**`detach_last_car`**
- Time: O(1) — direct tail access.
- Space: O(1) — no extra memory used.

**`to_reverse_list`**
- Time: O(N) — traverses all N nodes from tail to head.
- Space: O(N) — stores all N car IDs in the result list.

**`is_valid_ticket_code`**
- Time: O(1) — fixed-length checks only.
- Space: O(1) — no extra data structures.

**`count_priority_labels`**
- Time: O(N) — visits each label exactly once.
- Space: O(N) — recursion depth equals the length of the list.

**`clean_radio_message`**
- Time: O(N) — visits each character exactly once.
- Space: O(N) — recursion depth equals the length of the message.

## Edge-case checklist
- [x] empty train
- [x] one train car
- [x] invalid ticket code
- [x] empty label list
- [x] empty message
- [x] one-character or all-space message

## Assistance & Sources
- **AI used?** Y
- **What it helped with:** Structuring the recursive base cases and
  doubly linked list pointer updates.
- **Other sources used:** Python Official Documentation for `str.startswith`
  and `str.isdigit`.