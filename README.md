# **​​Dart Parallel Workers Challenge**

**Mission Codename:** *Cerebrum-Split: The Isolate Uprising*

In 2097, the global super-AI MONARCH went rogue. Humanity’s defense system now depends on parallel human-like micro-cores — similar to Dart isolates, independent minds with no shared memory.

You must simulate a distributed cognitive defense cluster.

### **What your program must do**

1. **Ask the user for**

   * `n` \= how many numbers to generate

   * `k` \= how many isolates to use (workers)

2. **Generate a list** of integers from `0` to `n-1`.

3. **Split the list into `k` parts**.

4. **Spawn `k` isolates**, each isolate receives one part of the list.

5. Each isolate must compute a function `f(x)` for every number in its segment.

### **The required function**

For each `x` in that segment:

`f(x) = (x² mod 97) XOR (reverse_bits(x) mod 89)`

You must implement `reverse_bits` yourself.

For reversebits(x), you need to convert x to binary (make sure that you use the minimum number of bits required to represent x). Then reverse the order of the bits and convert back to decimal.

### **Each isolate must return:**

* The **sum** of all `f(x)`

* The **most frequent** `f(x)` value in its segment

* A **weirdness score** \= count of `f(x)` values that end in digit `7` **OR** are **prime numbers**

### **After isolates finish:**

Your main program must output **final combined results**:

| Result | Meaning |
| ----- | ----- |
| Total sum | Sum of all segments’ sums |
| Global most frequent | Overall most common `f(x)` value |
| Total weirdness score | Sum of weirdness scores from all isolates |

---

## **Rules**

* Use **Dart isolates** (`Isolate.spawn`)

* Use **SendPort/ReceivePort**

* No third-party compute libraries

* No shared memory — only message passing

* Must manually implement:  
   reverse bits  
   prime check  
   frequency count

---

## **🎁 Bonus Points**

| Challenge | Points |
| ----- | ----- |
| Measure the execution time per isolate and the total execution time | \+2 |
| Find the most efficient isolate (efficiency = segment length/execution time) | \+2 |
