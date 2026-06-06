# Testing Tools - Detailed Notes

## Load Testing with JMeter

Load testing is a critical aspect of software quality assurance that evaluates how a system performs under a specific workload. Apache JMeter is an open-source tool designed for load testing and performance measurement of web applications.

---

## Step-by-Step Guide to Load Testing with JMeter

### Step 1: Install Java

JMeter requires Java to run. Install Java JDK or JRE (version 8 or higher).

**Installation Steps:**
1. Download Java from Oracle's website
2. Run the Java installer
3. Accept the license agreement
4. Complete the installation

**Verification:**
```bash
java -version
```

---

### Step 2: Download JMeter

Download Apache JMeter from the official website.

**Download URL:** https://jmeter.apache.org/download_jmeter.cgi

**Requirements:**
- Apache JMeter 5.1 or later (requires Java 8+)

**Download Options:**
- Binary: `apache-jmeter-5.1.tgz` or `apache-jmeter-5.1.zip`
- Source: Available for compilation

---

### Step 3: Install JMeter

JMeter doesn't require traditional installation — it runs directly from the extracted files.

**Installation Steps:**
1. Extract the downloaded archive
2. Navigate to the `bin` directory
3. Run `jmeter.bat` (Windows) or `jmeter.sh` (Linux/Mac)

**Key Files in `bin` Directory:**

| File | Description |
|------|-------------|
| `jmeter.bat` / `jmeter.sh` | Main JMeter executable |
| `ApacheJMeter.jar` | Core JMeter application |
| `jmeter.properties` | Configuration properties |
| `create-rmi-keystore` | RMI keystore creation script |
| `report-template/` | Report templates |
| `templates/` | Test plan templates |

**Starting JMeter:**
```bash
# Windows
jmeter.bat

# Linux/Mac
./jmeter.sh
```

---

### Step 4: Configure HTTP Request Samplers

HTTP Request samplers define the requests that JMeter will send to the server.

#### Creating a Test Plan

1. Open JMeter GUI
2. Create a new Test Plan
3. Add a Thread Group (simulates users)
4. Add HTTP Request samplers to the Thread Group

#### Configuring HTTP Request: HomePage

```
HTTP Request Configuration:
├── Name: HomePage
├── Web Server:
│   ├── Protocol: http
│   └── Server Name or IP: flex.nu.edu.pk
├── HTTP Request:
│   ├── Method: GET
│   ├── Path: /
│   ├── Redirect Automatically: ✓
│   ├── Follow Redirects: ✓
│   └── Use KeepAlive: ✓
└── Parameters: (none for basic request)
```

#### Configuring HTTP Request: MAIN

```
HTTP Request Configuration:
├── Name: MAIN
├── Web Server:
│   ├── Protocol: http
│   └── Server Name or IP: flex.nu.edu.pk
├── HTTP Request:
│   ├── Method: GET
│   ├── Path: /Home/
│   ├── Redirect Automatically: ✓
│   ├── Follow Redirects: ✓
│   └── Use KeepAlive: ✓
└── Parameters: (none for basic request)
```

---

### Step 5: Add Listeners

Listeners collect and display the results of test execution.

**How to Add Listeners:**
1. Right-click on the Thread Group or HTTP Request
2. Select Add → Listener
3. Choose the desired listener type

**Available Listeners:**

| Listener | Purpose |
|----------|---------|
| **View Results in Table** | Displays results in a tabular format |
| **Graph Results** | Shows results as a graph |
| **Summary Report** | Provides summary statistics |
| **Aggregate Report** | Shows aggregate statistics |
| **View Results Tree** | Shows detailed request/response data |
| **Assertion Results** | Displays assertion results |
| **Backend Listener** | Sends results to external systems |

---

### Step 6: View Results in Table

The "View Results in Table" listener provides a structured view of test results.

**Table Columns:**

| Column | Description |
|--------|-------------|
| **Sample#** | Sequential number of the request |
| **Start Time** | Time when the request started |
| **Thread Name** | Identifier for the thread (user) |
| **Label** | Name of the HTTP Request sampler |
| **Sample Time** | Time taken to complete the request (ms) |
| **Status** | Success (✓) or Failure (✗) |
| **Bytes** | Size of the response data |
| **Sent Bytes** | Size of the request data |
| **Latency** | Time from request sent to first response byte received |
| **Connect Time** | Time taken to establish connection |

**Example Results Table:**

| Sample# | Start Time | Thread Name | Label | Sample Time | Status | Bytes | Sent Bytes | Latency | Connect Time |
|---------|------------|-------------|-------|-------------|--------|-------|------------|---------|--------------|
| 1 | 13:47:52.119 | Users 1-57 | HomePage | 1232 | ✓ | 15160 | 238 | 56 | 26 |
| 2 | 13:47:52.129 | Users 1-42 | HomePage | 1014 | ✓ | 15160 | 238 | 56 | 26 |
| 3 | 13:47:52.255 | Users 1-56 | HomePage | 898 | ✓ | 15160 | 238 | 79 | 29 |
| 4 | 13:47:51.977 | Users 1-27 | HomePage | 1175 | ✓ | 15160 | 238 | 56 | 23 |
| 5 | 13:47:51.967 | Users 1-26 | HomePage | 1199 | ✓ | 15160 | 238 | 47 | 29 |

---

### Step 7: Graph Results Interpretation

The Graph Results listener provides visual representation of test results.

**Graph Elements:**

| Element | Description |
|---------|-------------|
| **Data** (blue dots) | Individual sample response times |
| **Average** (green line) | Average response time trend |
| **Median** (purple line) | Median (50th percentile) response time |
| **Deviation** (red line) | Standard deviation of response times |
| **Throughput** | Number of requests per unit time |

**Graph Statistics:**

| Statistic | Description |
|-----------|-------------|
| **No of Samples** | Total number of requests executed |
| **Latest Sample** | Response time of the most recent request |
| **Deviation** | Standard deviation of response times |
| **Throughput** | Requests per second (or per minute) |
| **Average** | Mean response time across all samples |

**Interpreting the Graph:**
- **Stable graph**: Response times are consistent (low deviation)
- **Increasing trend**: Performance degrades under load
- **Spike**: One or more requests took significantly longer
- **High throughput**: System handles many requests efficiently

---

## Practical Load Testing Example: flex.nu.edu.pk

### Scenario

Test the performance of the FLEX (Faculty Link for Education Excellence) portal at National University.

### Test Configuration

```
Test Plan: FLEX Load Test
├── Thread Group: Users
│   ├── Number of Threads: 200 (simulated users)
│   ├── Ramp-Up Period: 10 seconds
│   ├── Loop Count: 1 (single iteration per thread)
│   └── HTTP Request Samplers:
│       ├── HomePage
│       │   ├── Server: flex.nu.edu.pk
│       │   ├── Path: /
│       │   └── Method: GET
│       └── MAIN
│           ├── Server: flex.nu.edu.pk
│           ├── Path: /Home/
│           └── Method: GET
├── Listeners:
│   ├── View Results in Table
│   └── Graph Results
└── Summary Report
```

### Results Interpretation

#### Tabular Results Analysis

From the sample results:

| Metric | Value | Interpretation |
|--------|-------|----------------|
| **Average Sample Time** | ~1,100 ms | Average response time across all requests |
| **Minimum Sample Time** | ~770 ms | Fastest response time |
| **Maximum Sample Time** | ~1,389 ms | Slowest response time |
| **Average Latency** | ~60 ms | Time to first byte |
| **Average Connect Time** | ~27 ms | Connection establishment time |
| **Bytes Received** | 15,160 bytes | Consistent response size |
| **Sent Bytes** | 238 bytes | Request size |
| **All Statuses** | ✓ (Success) | All requests completed successfully |

#### Graph Results Analysis

| Statistic | Value | Interpretation |
|-----------|-------|----------------|
| **No of Samples** | 200 | Total requests executed |
| **Latest Sample** | 68 ms | Most recent response time |
| **Deviation** | 196 ms | Moderate variation in response times |
| **Throughput** | ~18 requests/second | System throughput |
| **Average** | ~1,050 ms | Mean response time |

### Key Observations

1. **Success Rate**: 100% — All 200 requests completed successfully
2. **Response Time**: Average around 1 second — acceptable for a web portal
3. **Consistency**: Response times vary between 770ms and 1,389ms — moderate variation
4. **Throughput**: ~18 requests per second — good throughput for the server
5. **Latency**: Low latency (45-94ms) — network connection is efficient
6. **Connection Time**: Fast connection establishment (21-52ms)

---

## Load Testing Best Practices

| Best Practice | Description |
|---------------|-------------|
| **Start with baseline** | Test with minimal load to establish baseline performance |
| **Gradual ramp-up** | Increase load gradually to identify breaking points |
| **Realistic scenarios** | Simulate real user behavior and patterns |
| **Monitor server resources** | Track CPU, memory, disk I/O during tests |
| **Test different endpoints** | Test all critical user journeys |
| **Compare results** | Compare with previous test runs to identify regressions |
| **Document findings** | Record all test configurations and results |

---

## Common Load Testing Metrics

| Metric | Description | Good Target |
|--------|-------------|-------------|
| **Response Time** | Time to complete a request | < 2 seconds |
| **Throughput** | Requests per second | Depends on application |
| **Error Rate** | Percentage of failed requests | < 1% |
| **Latency** | Time to first byte | < 100 ms |
| **Concurrent Users** | Number of simultaneous users | Depends on capacity |
| **Resource Utilization** | CPU, memory usage | < 80% |

---

## Key Connections

- **Load Testing** validates **Performance** quality attribute (from Quality Management)
- **JMeter Configuration** involves **HTTP Request Samplers** and **Listeners**
- **Results Interpretation** requires understanding of **Response Time**, **Throughput**, and **Error Rate**
- **Practical Testing** (flex.nu.edu.pk example) demonstrates real-world application
- **Best Practices** ensure reliable and meaningful test results
- **Metrics** connect load testing to quality management goals

---

## Quick Reference

| Step | Action |
|------|--------|
| 1 | Install Java (JDK/JRE 8+) |
| 2 | Download Apache JMeter |
| 3 | Extract and run `jmeter.bat` or `jmeter.sh` |
| 4 | Create Test Plan → Thread Group → HTTP Request Samplers |
| 5 | Configure server, path, method for each request |
| 6 | Add Listeners (View Results in Table, Graph Results) |
| 7 | Run test and analyze results |
| 8 | Interpret graph statistics and tabular data |

---

## Common Mistakes

| Mistake | Correction |
|---------|------------|
| Confusing latency with response time | Latency = time to first byte; Response time = total request time |
| Assuming higher throughput always means better performance | Throughput depends on request complexity and server capacity |
| Ignoring error rate in results | Even 99% success can mean 2 failed requests out of 100 |

## Exam Traps

| Trap | Why It's Tricky | Correct Answer |
|------|----------------|----------------|
| "200 users means 200 simultaneous requests" | Threads are simulated users, not necessarily simultaneous | JMeter simulates concurrent users through thread groups |

## Active Recall Questions

1. What are the 7 steps to perform load testing with JMeter?
2. What is the difference between latency and response time?
3. Name 4 JMeter listeners.
4. What is throughput?
5. What is a good target for error rate?

## Potential Exam Questions

1. Describe the steps to set up a load test in JMeter.
2. Explain how to interpret JMeter graph results.
3. What metrics should you monitor during load testing?
4. Compare tabular and graphical result presentation in JMeter.

## Topic Summary

Apache JMeter is an open-source tool for load testing and performance measurement of web applications. Load testing with JMeter follows 7 steps: install Java, download JMeter, extract and run, create Test Plan with Thread Group and HTTP Request samplers, configure server/path/method for each request, add listeners (View Results in Table, Graph Results), run and analyze. HTTP Request samplers define what requests JMeter sends. Listeners collect and display results. Key metrics include response time, throughput, error rate, latency, and resource utilization. The FLEX portal example demonstrates 200 simulated users hitting HomePage and MAIN endpoints, showing 100% success rate, approximately 1 second average response time, and 18 requests per second throughput. Best practices include baseline testing, gradual ramp-up, realistic scenarios, and documenting findings.
