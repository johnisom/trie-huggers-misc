# Remove Duplicates from Sorted List II #

## Understanding the Problem ##

Given a sorted linked list, delete elements if there are more than 1 of a
type. For example if there is a 1, two 2s, and a 3, return 1 and 3, leaving
out *all* 2s.

## Examples ##

Example 1:
- Input: 1→2→3→3→4→4→5
- Return: 1→2→5

Example 2:
- Input: 1→1→1→2→3
- Return: 2→3

## Data Structures ##

- 3 pointers:
  - Fast
  - Medium
  - Slow
- Dummy head

## Algorithm ##

(dummy)→1→3→4→8→9→(NULL)
      s
        m f

1. initialize pointers
    - s ← dummy
    - m ← dummy
    - f ← head
2. while f
   1. move m and f forward 1
      - m = f
      - f = f.next
   2. move all forward until m is on the first repeated number or f is null
      - while f && m.val != f.val
        - s = m
        - m = f
        - f = f.next
   3. Break if f is null
   4. Move m and f forward until m is on last repeated num
      - while f && m.val == f.val
        - m = f
        - f = f.next
   5. link s to f
3. return dummy.next
