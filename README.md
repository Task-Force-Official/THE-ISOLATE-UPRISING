# **🧠 Dart Parallel Workers Challenge**

### **"Multi-Mind Matrix"**

Welcome to the **Multi-Mind Matrix** — a coding challenge designed to showcase the power of **parallel computation in Dart** using **Isolates** (a.k.a. Dart Parallel Workers)\!

Most languages use threads.  
 **Dart goes further** — each isolate has its own memory, allowing safe true parallelism without shared-state issues.

Your mission?  
 Harness Dart’s isolates to break down a heavy compute task and run it in parallel — faster, smarter, and cleaner.

---

## **🎯 Objective**

Write a Dart program that:

1. Splits a computationally intensive job into multiple subtasks

2. Executes each subtask in **parallel using isolates**

3. Collects and combines results efficiently

4. Benchmarks parallel vs single-thread speed

---

## **⚙️ Task Description**

You are given a large list of integers (e.g., 1 to 10,000,000).

You must:

* Divide it into chunks

* Use isolates to compute the **sum of squares** for each chunk

* Combine the partial results into a final answer

* Print time taken for:

  * ✅ Single isolate (normal execution)

  * ✅ Multi-isolate parallel execution

---

## **🧩 Rules**

| Feature | Requirement |
| ----- | ----- |
| Language | Dart |
| Unique Concept | **Isolates (Dart Parallel Workers)** |
| Input | Auto-generated list size & chunk count |
| Output | ✅ Parallel result & time ✅ Single-thread result & time ✅ Speed-up factor |
| Bonus | Visual output formatting or logs showing isolates working |
| Avoid | Threading libraries, external compute libs |

---

## **🏆 Judging Criteria**

| Category | Points |
| ----- | ----- |
| Correct implementation | 40 |
| Efficient parallel design | 25 |
| Code readability | 15 |
| Benchmark output clarity | 10 |
| Bonus creativity | 10 |

---

## **💡 Hints**

* Use `Isolate.spawn()`

* Communicate via `ReceivePort` & `SendPort`

* Measure performance using `Stopwatch()`

* Plan chunk sizes smartly — too many isolates \= slow

---

## **🧪 Example Output Format**

(Not actual expected values)

`Single-thread sum: 333283335000`  
`Time: 410ms`

`Parallel (4 isolates) sum: 333283335000`  
`Time: 120ms`

`Speed improvement: 3.41x faster 🚀`

---

## **📦 File Structure**

`main.dart`

Everything inside one file.

---

## **🏁 Deliverables**

When submitting, include:

* ✅ `main.dart`

* ✅ Console output screenshot

* ✅ Short explanation (3–5 lines)

---

## **🌟 Challenge Theme**

**Think beyond loops. Think like clusters.**

Good luck — welcome to the **Multi-Mind Matrix**.  
 Show us how many brains your code can think with\! 🧠⚡

