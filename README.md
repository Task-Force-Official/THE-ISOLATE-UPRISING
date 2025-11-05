# 🚨 TASK FORCE: THE ISOLATE UPRISING 🚨

**Mission Codename:** *Cerebrum-Split: The Isolate Uprising*

In 2097, the global super-AI MONARCH went rogue. Humanity’s defense depends on parallel human-like micro-cores — simulated here by Dart isolates. Your mission: build a Dart program that distributes computation across isolates and aggregates the results.

---

## Short description

Create a Dart program that accepts user input, generates numbers, distributes them among parallel isolates, computes a specified function per number, and aggregates each isolate's results into a final report.

---

## Task Requirements

1. **Input**

   * Prompt the user for `n` (how many numbers to generate) and `k` (how many isolates/workers to spawn).

2. **Generate**

   * Create the list `[0, 1, 2, ..., n-1]`.

3. **Split**

   * Divide the list into `k` segments as evenly as possible.

4. **Spawn isolates**

   * Use `Isolate.spawn` for each segment; communicate via `SendPort` / `ReceivePort`.

5. **Per-isolate computation**
   For each `x` in the isolate’s segment compute:

   ```text
   f(x) = (x^2 mod 97) XOR (reverse_bits(x) mod 89)
   ```

   * Implement `reverse_bits(x)` manually: convert `x` to binary using the minimum number of bits required to represent `x`, reverse those bits, convert back to decimal.
   * Implement a manual `isPrime(x)` check (no library calls).
   * Manually count frequencies of `f(x)` values.

6. **Each isolate returns**

   * Sum of all `f(x)` values in its segment.
   * The most frequent `f(x)` value in its segment.
   * Weirdness score: count of `f(x)` values that either end in digit `7` **OR** are prime numbers.

7. **Main isolate**

   * Collect results from all isolates and print a clear report including per-isolate stats and aggregated totals.

* Must use Dart isolates (`Isolate.spawn`) and `SendPort`/`ReceivePort` for all inter-isolate communication.
* No shared memory; only message passing.
* No third-party compute libraries.
* Implement `reverse_bits`, `isPrime`, and frequency counting yourself.
* Program should accept interactive input (stdin) and be robust to small `n`/`k` values.

## Bonus Objectives

* **Measure execution time per isolate and total time** (+2)
* **Find the most efficient isolate** (efficiency = segment length / execution time) (+1)
* **Calculate total sum of all `f(x)` and total weirdness score** (+1)
* **Find the global most frequent `f(x)` across all isolates** (+1)

## Submission (files to hand in)

Package your submission as `Lastname_Firstname_TaskForce_Dart.zip` containing:

* `main.dart` — the working Dart program (clean, commented).
* `screenshot.png` — execution screenshot showing user inputs and program output.
* `report.txt` — brief (1–2 paragraphs) explanation of your approach and any edge cases handled.
* Optional: Screenshots of Bonus Objective Outputs + txt file with findings in Bonus Objective (execution time, most efficient isolate etc..)

Your program must print, for each isolate:

* Isolate index and its assigned segment range.
* Per-isolate sum of `f(x)` values.
* Per-isolate most frequent `f(x)`.
* Per-isolate weirdness score.

Also print aggregated totals and (if attempted) bonus metrics.

## Brief Hints

* Test with small `n` (e.g., 20–100) first to validate correctness.
* Ensure `reverse_bits` uses *minimal bits* required to represent `x` (e.g., `x = 5` -> `101` -> reverse -> `101` -> 5).
* Time measurements: capture `DateTime.now().microsecondsSinceEpoch` before/after isolate work.

## Resources

* Dart Isolates: [https://dart.dev/language/isolates](https://dart.dev/language/isolates)
* Dart concurrency guide: [https://dart.dev/tutorials/language/concurrency](https://dart.dev/tutorials/language/concurrency)

Good luck, Operative. MONARCH is listening — make every isolate count.
