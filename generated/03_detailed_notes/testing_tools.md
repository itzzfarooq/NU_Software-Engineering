# Load Testing with JMeter — Detailed Notes

## Topic Overview

Load testing is a type of performance testing that simulates real-world user traffic on a software system to determine how it behaves under expected and peak load conditions. Apache JMeter is an open-source tool designed specifically for load testing and measuring performance. These notes cover JMeter installation, configuration, test plan creation (Thread Groups, HTTP Request Samplers, Listeners), test execution, and result analysis.

## Why This Topic Exists

Software systems must handle concurrent users without crashing, slowing down, or producing errors. Without load testing, teams deploy blindly — hoping the server can handle traffic. JMeter lets engineers:
- Identify bottlenecks before users do.
- Determine maximum capacity (how many concurrent users a system can support).
- Validate that SLAs (Service Level Agreements) for response times are met.
- Compare performance before and after changes (regression testing).

## Core Concepts

### Load Testing
The process of putting demand on a system and measuring its response. JMeter simulates multiple users sending requests to a server simultaneously. Metrics collected include response time, throughput, error rate, and resource usage.

### Stress Testing
A subset of load testing where the load is increased beyond normal operational capacity to find the breaking point. The goal is to see how the system fails and whether it recovers gracefully.

### Key Terms
- **Sampler**: The component that sends a request (e.g., HTTP Request) to the server.
- **Thread Group**: Defines the pool of virtual users. Each thread represents one user.
- **Listener**: Records and visualizes the results (Table, Graph, Tree).
- **Throughput**: Number of requests processed per unit time (e.g., requests/sec).
- **Latency**: Time between sending a request and receiving the first byte of the response.
- **Sample Time / Response Time**: Total time from request send to full response received.

---

## JMeter Setup

### Step 1 — Install Java
JMeter requires Java 8 or higher.
1. Download Java from the official Oracle or OpenJDK site.
2. Run the installer (accept license, choose destination).
3. Verify with: `java -version`

### Step 2 — Download JMeter
1. Go to https://jmeter.apache.org/download_jmeter.cgi
2. Download the binary archive (`.zip` for Windows, `.tgz` for Linux/Mac).
3. Version shown in course: Apache JMeter 5.1 / 5.4.1 (requires Java 8+).

### Step 3 — Install JMeter
1. Extract the archive to a folder (e.g., `C:\Users\Administrator\Downloads\apache-jmeter-5.4.1`).
2. Navigate to the `bin/` subdirectory. Key files include:
   - `jmeter.bat` — Windows launcher for GUI mode.
   - `jmeter.sh` — Linux/Mac launcher.
   - `jmeter.properties` — Main configuration file.
3. **Launch**: On Windows, double-click or run `bin/jmeter.bat`. The JMeter GUI opens with a blank Test Plan.

---

## Test Configuration

### Test Plan (Root Element)
The top-level container for all test elements.
- **Name** and **Comments** are user-defined (e.g., "daraz" project).
- Options: Run Thread Groups consecutively; Functional Test Mode (saves response/sampler data — may hurt performance).

### Thread Group
Defines the virtual users.
- Add: Right-click Test Plan → Add → Threads (Users) → Thread Group.
- Configuration fields:
  - **Number of Threads (users)**: How many concurrent virtual users.
  - **Ramp-Up Period (seconds)**: Time to spin up all threads. Prevents sudden load spikes.
  - **Loop Count**: How many times each thread executes. "Infinite" for continuous load.
- Each thread runs the samplers under the Thread Group in order.

### Samplers
Samplers send requests of a specific protocol to the server.
- **HTTP Request** sampler: Sends HTTP/HTTPS requests (GET, POST, etc.).
- Configuration fields for HTTP Request:
  - **Protocol**: `http` or `https`.
  - **Server Name or IP**: e.g., `flex.nu.edu.pk`.
  - **Path**: e.g., `/` for homepage, `/Home/` for a sub-page.
  - **Method**: GET, POST, PUT, DELETE, etc.
  - **Parameters**: Key-value pairs sent with the request.
  - **Redirect options**:
    - `Redirect Automatically` — follows redirects without extra sample.
    - `Follow Redirects` — follows redirects but records each as a separate sample.
    - `Use KeepAlive` — reuses TCP connections for efficiency.

### Listeners
Listeners capture and display test results. Common types:
- **View Results in Table**: Shows each sample as a row with metrics (Sample Time, Status, Bytes, Latency, Connect Time).
- **Graph Results**: Plots data points as lines (Average, Median, Deviation, Throughput).
- **Summary Report**: Aggregated statistics per label.

### Adding Elements
Right-click any element in the Test Plan tree to add:
- Logic Controllers, Samplers, Pre/Post Processors, Timers, Assertions, Config Elements, Listeners.
- **Action after a Sampler error**: Stop Thread, Stop Test, Stop Test Now, or Start Next Loop.

---

## Test Execution

### Running the Test
1. Ensure the Test Plan is configured with a Thread Group + at least one Sampler + at least one Listener.
2. Click the green **Start** button (or Run → Start).
3. JMeter spawns threads (virtual users) and begins sending requests.
4. Listeners populate in real time as samples complete.

### Analyzing Results — Table View
The **View Results in Table** listener displays columns:
| Column | Meaning |
|---|---|
| Sample # | Sequential ID of the request |
| Start Time | Timestamp when request began |
| Thread Name | Virtual user identifier (e.g., "Users 1-54") |
| Label | Name of the Sampler (e.g., "HomePage") |
| Sample Time (ms) | Total response time |
| Status | Green circle = success; Red = failure |
| Bytes | Size of the response |
| Sent Bytes | Size of the request |
| Latency | Time to first byte |
| Connect Time | Time to establish TCP connection |

Example: Sample #1 for HomePage shows 1123 ms response time, 15160 bytes, 58 ms latency, 20 ms connect time — all successful (green).

### Analyzing Results — Graph View
The **Graph Results** listener displays:
- **Data**: Raw sample points.
- **Average**: Mean response time across all samples.
- **Median**: Middle value of response times.
- **Deviation**: Standard deviation (spread of response times).
- **Throughput**: Requests per minute/second.
- Summary stats at bottom: Number of Samples, Latest Sample, Throughput.

Trend: If the graph trends upward over time, the system is degrading under sustained load.

---

## Detailed Explanations

### Step-by-Step: Create a Basic JMeter Test
1. Launch JMeter (`jmeter.bat` / `jmeter.sh`).
2. Rename Test Plan to your project name.
3. Add Thread Group (set thread count, ramp-up, loop count).
4. Add HTTP Request Defaults (optional — sets base server/port shared by all requests).
5. Add HTTP Request Sampler under Thread Group (set protocol, server, path, method).
6. Add Listener (View Results in Table and/or Graph Results).
7. Save the Test Plan (`.jmx` file).
8. Click Start.
9. Observe results in Listeners.

### Relationships Between Components
- **Test Plan** → **Thread Group** → **Samplers** + **Listeners**
- **Thread Group** controls *who* (how many users) and *when* (ramp-up, loops).
- **Samplers** define *what* request is sent.
- **Listeners** show *what happened* (metrics).
- **HTTP Request Defaults** let you centralize server/port settings instead of repeating them per Sampler.

### Ramp-Up Explained
Ramp-Up prevents the "thundering herd" problem. If 100 users start simultaneously, the server may be overwhelmed immediately. A 100-second ramp-up starts 1 user per second, giving the server time to warm up and reveal gradual degradation.

---

## Common Mistakes / Exam Traps

| Mistake | Why It Matters |
|---|---|
| Forgetting to install Java first | JMeter will not launch |
| Running GUI mode for production-scale tests | GUI mode consumes memory; use CLI (`jmeter -n -t test.jmx`) for real load tests |
| Not configuring Follow Redirects | Redirect responses (301/302) will appear as errors or incorrect samples |
| Setting ramp-up = 0 for large thread counts | All users hit server at once; may cause false failures |
| Misinterpreting Latency vs Sample Time | Latency = time to first byte; Sample Time = full response receipt |
| Ignoring Connect Time for persistent vs non-persistent connections | High connect time suggests connection overhead (disable KeepAlive intentionally as a test) |
| Using only one Listener type | Table is good for detail; Graph is good for trends; both together give full picture |
| Not saving the Test Plan before running | JMeter can crash and lose configuration |

---

## Active Recall Questions

1. What three things must every JMeter Test Plan contain?
2. What is the difference between Latency and Sample Time?
3. Why would you use the "Follow Redirects" option instead of "Redirect Automatically"?
4. What does a rising trend line in the Graph Results listener indicate?
5. What is the purpose of Ramp-Up in a Thread Group?
6. How do you launch JMeter on Windows? On Linux?
7. What Java version is required for JMeter 5.1+?
8. What is the difference between load testing and stress testing?
9. In the Table view, what does a red status indicate?
10. What command-line flag runs JMeter in non-GUI mode?

---

## Potential Exam Questions

1. **Short Answer**: Describe the steps to configure an HTTP Request sampler in JMeter to test a website's homepage.
2. **Diagram/Explain**: Draw and label the hierarchy of a JMeter Test Plan. Explain the role of each component.
3. **Comparison**: Compare the View Results in Table listener with the Graph Results listener. When would you prefer one over the other?
4. **Scenario**: A server returns 302 redirect responses and your JMeter test shows all samples as failures. What is the likely cause and how do you fix it?
5. **Calculation**: If a Thread Group has 50 threads, a ramp-up of 25 seconds, and a loop count of 2, how many total requests will be sent? (Answer: 50 × 2 = 100)
6. **Definition**: Define throughput and latency in the context of JMeter results.
7. **Problem-Solving**: Your load test shows increasing response times as the test progresses. What does this suggest about the system under test?
8. **True/False**: You must configure HTTP Request Defaults in every JMeter test plan. (False — they are optional convenience elements.)
9. **Essay**: Explain the relationship between Thread Groups, Samplers, and Listeners in JMeter. How does data flow between them?
10. **Design**: Propose a JMeter test plan for an e-commerce site's login and search functionality. Specify thread count, ramp-up, samplers, and listeners you would use.

---

## Topic Summary

- JMeter is an open-source load testing tool requiring Java 8+.
- Setup involves: Install Java → Download JMeter → Extract → Run `jmeter.bat`/`jmeter.sh`.
- Core elements: Test Plan (root), Thread Group (virtual users), Samplers (requests), Listeners (results).
- HTTP Request Sampler: Configure protocol, server, path, method, parameters, redirect behavior.
- Listeners: Table View (per-sample detail), Graph View (trends over time).
- Key metrics: Sample Time, Latency, Connect Time, Throughput, Bytes, Status.
- Ramp-Up is critical — prevents server shock on test start.
- For production tests, use CLI mode (`jmeter -n -t plan.jmx -l results.jtl`).
- Common exam traps: confusing latency vs sample time, forgetting Java, misconfiguring redirects, ignoring ramp-up.