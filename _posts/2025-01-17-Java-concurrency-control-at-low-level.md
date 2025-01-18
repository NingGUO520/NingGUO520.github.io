## Java Lock-free Concurrency Control

Java achieves concurrency control through two primary mechanisms:
- Lock-Based Mechanism (Pessimistic Locking)
- Lock-Free Mechanism (Optimistic Locking)

### Lock-free Mechanism (optimistic lock)

Optimistic locking operates without using traditional locks. Instead, it assumes minimal contention and 
detects conflicts only when they occur. It uses Compare-And-Swap (CAS), a low-level atomic operation 
supported by modern CPUs.

Compare-And-Swap (CAS)
Definition: CAS is a hardware-supported atomic operation that updates a memory location only if its current value matches an expected value.
Operation Signature:
CAS(memory location, expected value, new value)

Parameters:
- Memory location: location where variable is stored
- Expected value: The value the variable is expected to have.
- New value: The value to update the variable with if the expectation is met.

How CAS Works
1. Load or read the variable from memory.
2. Compare the memory's current value with the expected value.
3. If they are equal: Update the memory location with the new value.
4. If they are not equal: Retry the operation (go back to step 1).

use case in java
- AtomicInteger
- AtomicBoolean
- AtomicReference
 
