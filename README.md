# concurrency

### 1. LAZY Read-Write (25 marks)
**Objective:** Simulate a file manager's behavior under load, handling multiple user requests for reading, writing, and deleting files concurrently.

#### Key Concepts:
- **Concurrency Management:** Use threads, locks, condition variables, or semaphores to simulate real-time operations.
- **User Requests:** Each operation (READ, WRITE, DELETE) has a specific processing time and concurrency limits.
- **Cancellation:** Users may cancel requests if they are not processed within a specified time.

#### Input Format:
- Time taken for operations (r, w, d).
- Number of files (n), maximum concurrent users (c), and maximum wait time (T).
- User requests with ID, file number, operation, and request time.

#### Rules:
- LAZY waits for 1 second after receiving a request before processing.
- Multiple users can read simultaneously, but writing and deleting are exclusive operations.
- Requests can be declined if the file is invalid or deleted.

#### Output Requirements:
- Chronological logs of events, including request submissions, processing starts, cancellations, and completions.

---

### 2. LAZY Sort (35 marks)
**Objective:** Implement a distributed sorting mechanism that dynamically selects sorting algorithms based on the number of files.

#### Sorting Strategy:
- **Threshold-Based Decision:**
  - Use **Distributed Count Sort** for fewer than 42 files.
  - Use **Distributed Merge Sort** for 42 or more files.

#### Input Format:
- An integer indicating the total number of files.
- Each file's attributes (name, ID, timestamp) on separate lines.
- The column used for sorting (one of "Name", "ID", "Timestamp").

#### Output Requirements:
- The name of the sorting column.
- The sorted list of files with attributes in the original order, separated by spaces.

### Implementation Considerations:
- The sorting should be efficient, activating nodes only as needed to minimize resource usage.
- Ensure coordination between nodes for effective distributed sorting.

