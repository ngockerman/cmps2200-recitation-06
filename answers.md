# CMPS 2200 Recitation 06
## Answers

**Name:** Natalie Gockerman
**Name:**_________________________


Place all written answers from `recitation-07.md` here for easier grading.



- **2)**
  W(n) for fib_recursive(n):
  W(n) = W(n - 1) + W(n - 2) + O(1)
  Base cases: W(0) = W(1) = O(1)
  Grows at the same rate of the fibonacci sequence:
  W(n) = O(2^n)

- **3)**
  S(n) for fib_recursive(n):
  S(n) = max(S(n - 1), S(n - 2)) + O(1)
  S(n - 1) >= S(n - 2) for n >= 2
  Therefore, S(n) = S(n - 1) + O(1) --> S(n) = Θ(n)

- **4)**
  When looking closely at the list counts and how it increments with the calls to fib_recursive I found that:
  Each time fib_recursive(n, counts) is called with value n = i, counts[i] is incremented.
  Understanding how the recursive call works, I see that each call to fib_recursve(n) where n>2 creates 2 more calls to fib_recursive for n-1 and n-2. Therefore, counts[i] grows similarly to Fn-i, meaning the value for i in the list counts will be proportional to the fibonnaci sequence value for n-i, but summed with the value of the prior call (higher i value). To visualize this look at this data:
  i = 7, Fn-i = 0 --> counts[i] = 1
  i = 6, Fn-i = 1 --> counts[i] = 1
  i = 5, Fn-i = 1 --> counts[i] = 2
  i = 4, Fn-i = 2 --> counts[i] = 3
  i = 3, Fn-i = 3 --> counts[i] = 5
  i = 2, Fn-i = 5 --> counts[i] = 8
  i = 1, Fn-i = 8 --> counts[i] = 13
  i = 0, Fn-i = 13   --> counts[i] = 21
  This pattern does not always work perfectly due to variability in base cases, but it is interesting that counts typically follows an inverse pattern to the typical fibonacci sequence.

- **6)**
  The maximum number of calls to fib_top_down is 2 because the first time a value is computed it is memoized, allowing the function to simply recall it rather than recomputing.
  Therefore W(n) = Θ(n) given each call will have one computation and one memory call of O(1)
  Then, S(n) = Θ(n) since the recursion chain is n --> n-1 --> 0

- **8)**
  The maximum number of times Fi will be read is 2 for fibs[i+1] and fibs[i+2].
  Therefore, W(n) is Θ(n) since there is one call for each i with work value of O(1)
  Then, S(n) is Θ(n) since each call is sequential and depends on the one before.
